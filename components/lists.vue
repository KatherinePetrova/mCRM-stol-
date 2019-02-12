<template>
	<div class="content" v-if="ready">
		<div class="header">
			<div class="about r-border child">
				<span class="about-name" @click="dropIt">Контакты</span>
				<transition name="slide">
				    <ul class="list" v-if="isDropped">
				      <li>Контакты</li>
				      <li>Компании</li>
				      <li>Все контакты и компании</li>
				    </ul>
				 </transition>
<!-- 
				<div class="table_type table_type__vertical">
					<div class="first_block block"></div>
					<div class="second_block block"></div>
					<div class="third_block block"></div>
				</div>
				<div class="table_type table_type__horrizontal table_type__activate">
					<div class="first_block block"></div>
					<div class="second_block block"></div>
					<div class="third_block block"></div>
				</div> -->
			</div>
<!-- 
			<div class="about r-border child dwm">
				<div>
					<span>День</span>
				</div>
				<div>
					<span>Неделя</span>
				</div>
				<div>
					<span>Месяц</span>
				</div>
			</div> -->

			<div class="search r-border child">
				<svg class="list-top-search__icon svg-icon svg-common--filter-search-dims">
					<use xlink:href="#common--filter-search">
						<svg viewBox="0 0 16 15" id="common--filter-search" width="100%" height="100%"><path id="chSearch" class="chcls-1" d="M6.493 12.994a6.5 6.5 0 1 1 6.5-6.5 6.5 6.5 0 0 1-6.5 6.5zm0-11.007a4.506 4.506 0 1 0 4.5 4.506 4.5 4.5 0 0 0-4.5-4.506zM16.01 14.11l-.894.9-3.108-2.632 1.38-1.388z"></path></svg>		
					</use>
				</svg>
				<input type="text" placeholder="Поиск и фильтр" class="input">
				<span class="deals">
					<span class="count">17216 контактов</span>
				</span>
			</div>

			<div class="setings child">
				<svg class="svg-icon svg-controls--button-more-dims">
					<use xlink:href="#controls--button-more">
						<svg viewBox="0 0 13 3" id="controls--button-more" width="100%" height="100%"><path id="dymore" class="dycls-1" d="M1.5 0A1.5 1.5 0 1 1 0 1.5 1.5 1.5 0 0 1 1.5 0zm5 0A1.5 1.5 0 1 1 5 1.5 1.5 1.5 0 0 1 6.5 0zm5 0A1.5 1.5 0 1 1 10 1.5 1.5 1.5 0 0 1 11.5 0z"></path></svg>		
					</use>
				</svg>		
				<button class="button__new_deal">
					<svg class="svg-icon svg-controls--button-add-dims">
						<use xlink:href="#controls--button-add">
							<svg viewBox="0 0 9 9" id="controls--button-add" width="100%" height="100%"><path id="dv_" data-name="+" class="dvcls-1" d="M9 5H5v4H4V5H0V4h4V0h1v4h4v1z"></path></svg>		
						</use>
					</svg>
					Добавить контакт
				</button>
			</div>
		</div>
		<div class="body">
			<table>
				<thead>
					<tr style="border-top: none;">
						<th style="color: #6e747a"><input type="checkbox">Наименование<div class="arrow"><img src="/arrow.png" alt=""></div></th>
						<th style="border-right: none">Компания</th>
					</tr>
				</thead>
				<tbody>
					<tr class="task" v-for="item in link">
						<td>
							<div><input type="checkbox"></div>
							<div class="info">
								<span>"{{item.contact.name}}"</span>
							</div>
							<div class="point"><span>&bull;</span></div>
						</td>
						<td>
							<div class="info">
								<span>{{item.company.name}}</span>
							</div>
						</td>
					</tr>
					
				</tbody>
			</table>
		</div>
	</div>
	<!-- <div class="loading" v-else>
        <div></div>
    </div> -->
</template>

<script>
import axios from 'axios'
export default {
	props: ['page'],
  components: {
  },
  data(){
	  return {
	  	ready: false,
		 count: this.page*40+1,
		 link: [],
		 isDropped: false,
	  }
  },
  methods: {
		dropIt() {
      		this.isDropped = !this.isDropped
    	}
	},
  async mounted(){
  	console.log(this.count)
  	try{

		var link = await axios(`http://crm.aziaimport.kz:3000/api/where/leads_company_contacts/${this.count}`, {
				method: 'post',
				withCredentials: true,
				data: {}
		});
		this.link = link.data;

		for (var i = 0; i < this.link.length; i++) {
			var contact = await axios(`http://crm.aziaimport.kz:3000/api/where/contacts/0`, {
				method: 'post',
				withCredentials: true,
				data: {where:{id:this.link[i].contact_id}}
			});
			console.log(contact);
			this.link[i].contact = contact.data[0];

			var company = await axios(`http://crm.aziaimport.kz:3000/api/where/leads_company/0`, {
				method: 'post',
				withCredentials: true,
				data: {where:{id:this.link[i].leads_company_id}}
			});
			console.log(company);
			this.link[i].company = company.data[0];
		}
		console.log(this.link);
  		this.ready = true;
  	} catch(e){
  		console.log(e)
  	}

  	
  }
}
</script>

<style scoped>
.loading {
  display: flex;
  justify-content: center;
  align-items: center;

  position: absolute;

  min-height: 100vh;
  min-width: calc(100%-70px);

  left: 70px;

  border-width: 20px;
<<<<<<< HEAD
  background-color: white;
=======

  background-color: #e5e5e5;
>>>>>>> 36b06867c853d58f76fc4d67da110dc9ccb8cd6c
}

.loading>div {
  background-color: white;

  height: 10em;
  width: 10em;

  border-radius: 50%;

  transition: 1s;

  animation-name: load;
  animation-duration: 5s;
  animation-iteration-count: infinite;
  animation-timing-function: ease-in-out;
}

@keyframes load {
  0% {height: 10em; width: 10em; background-color: rgba(140, 140, 240, 0.5)}
  25% {height: 5em; width: 5em; background-color: rgba(140, 240, 140, 0.5)}
  50% {height: 10em; width: 10em; background-color: rgba(240, 140, 140, 0.5)}
  75% {height: 5em; width: 5em; background-color: rgba(140, 140, 240, 0.5)}
  100% {height: 10em; width: 10em; background-color: rgba(140, 240, 140, 0.5)}
}
/*header*/
	.content{
		height: 100vh;
		width: 100%;
		background-color: #f5f5f5;
		position: relative;
		width: calc(100%-70px);
		left: 70px;
		position: absolute;
		top: 64px;
	}
	.header{
		height: 64px;
		width: calc(100%-70px);
		display: flex;
		flex-direction: row;
		border-bottom: 1px solid rgba(0,0,0,0.1);
		background-color: #ffffff;
		z-index: 999;
		position: fixed;
		top: 0;
	}
	.r-border{
		border-right: 1px solid rgba(0,0,0,0.1);
	}
	.header>.child{
		display: flex;
		height: 100%;
		padding: 1.5em 1.75em;
		width: auto;
	}
	.header>div.search{
		width: 70%;
		padding: 1.5em 1em;
	}
	.header>div.setings{
		padding: 1.5em 1em;	
	}

	.about-name{
		text-transform: uppercase;
		font-weight: 700;
		font-size: 0.95em;
		margin-right: 20px;
		white-space: nowrap;
		cursor: pointer;
	}
	.table_type{
		height: 100%; 
		display: flex;
		margin: 2.5px 5px;
		cursor: pointer;
	}
	.table_type__horrizontal{
		flex-direction: column;
		height: 80%;
		justify-content: space-between;
	}
	.table_type.table_type__activate>.block{
		background-color: #4c8bf7;
	}
	.table_type>.block{
		background-color: rgba(0,0,0,0.25);
		width: 2px;
		margin: 0 2px;
		height: 100%;
		display:block;
	}
	.table_type__horrizontal>.block{
		/*transform: rotate(90deg);*/
		width: 14px;
		margin: 0;
		height: 2px;
	}
	.table_type__vertical>.first_block{
		height: 100%;
	}
	.table_type__vertical>.second_block{
		height: 75%;	
	}
	.table_type__vertical>.third_block{
		height: 40%;
	}

	.search>svg{
		width: 20px;
		fill: #6e747a;
	}
	.search>.input{
		border: none;
		outline: none;
		font-size: 100%;
		width: 650px;
	}
	.search>.input::placeholder{
		color: rgba(0,0,0,0.33);
	}
	.deals>.count{
		color: rgba(0,0,0,0.33);
	}

	.setings>svg{
		width: 15px;
		margin: 0 0.5em;
	}
	.setings>button{
		margin: 0 0.5em;
		border-radius: 3px;
		white-space: nowrap;
		display: flex;
		justify-content: center;
		align-items: center;
		height: calc(100% + 1.5em);
		margin-top: -0.75em;
		text-transform: uppercase;
		font-weight: 700;
		padding: 0 0.5em;
	}
	.button__setings{
		border: 1px solid #dbdedf;
		color: #313942;
		background-color: #fcfcfc;
	}
	.button__new_deal{
		border: 1px solid #4077d6;
		background-color: #4c8bf7;
		color: #f5f5f5;
		fill: #f5f5f5;
	}
	.button__new_deal>svg{
		width: 20px;
		height: 25%;
	}
	.dwm {
		display: flex;
		align-items: center;
		color: #bcc0c7;
		text-transform: uppercase;
		font-weight: bold;
	}
	.dwm div {
		padding: 5px;
	}

	.list{
  			position: fixed;
  			top: 64px;
  			left: 70px;
  			width: 160px;
			margin: 0;
			padding: 0;
			list-style-type: none;
			transform-origin: top;
			transition: transform .4s ease-in-out;
			overflow: hidden;

	}
	.list li {
		    padding: 15px;
		    background-color: #d4d0d0;
		    border-bottom: solid thin #eee;
		    border-left: solid medium #cbc;
  		}
	.slide-enter, .slide-leave-to{
  		transform: scaleY(0);
	}
/*body*/
	.body {
		display: flex;
		padding: 15px;
	}
	table {
		width: 100%;
		border-collapse: collapse;
		background-color: #ffffff;
	}

	

	thead {
		color: #b9c0cb;
		text-transform: uppercase;
		font-weight: bold;
		width: 100%;
	}

	thead tr {
		padding: 0;
		height: 45px;
	}

	th {
		width: 50%;
		border-right: #e5e5e5 solid 1px;
		border-bottom: #e5e5e5 solid 1px;
		font-size: 13px;
		text-align: left;
		padding-left: 10px;
		position: relative;
	}

	tr {
		border-top: #e5e5e5 solid 1px;
		border-bottom: #e5e5e5 solid 1px;;
		width: 100%;
	}

	td {
		padding: 10px;
		position: relative;
	}

	td:first-child,th:first-child {
		padding-left: 50px;
	}

	table input {
		position: absolute;
		height: 20px;
		transform: scale(1.7);	
		left: 15px;
	}

	td input {
		height: 25px;
	}

	.groupTask{
		display: flex;
		align-items: center;
		height: 35px;
		padding-left: 50px;
		border-top: #f1f1f1 solid 1px;
		color: #e9e9e9;
		font-weight: bold;
	}

	.groupName {
		color: #92989b;
		font-weight: bold;
		height: 35px;
		font-size: 13px;
	}

	.task {
		height: 40px;
	}

	.info {
		display: flex;
		flex-direction: column;
		color: #7a7f85
	}

	.point {
		color: #b1b1b1;
		position: absolute;
		right: 10px;
		top: 3px;
		font-size: 25px;
		cursor: pointer;
	}

	.arrow {
		position: absolute;
		top: 15px;
		right: 13px;
		cursor: pointer;
		transform: rotate(270deg);
	}
	.arrow img {

		height: 8px;
		width: 5px;
	}
</style>