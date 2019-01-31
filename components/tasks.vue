<template>
	<div class="content">
		<transition name="fade">
			<div class="modal" v-if="show_modal">			
				<div class="modal_main" @click="show_modal=false">
					<div class="modal_body" v-on:click.stop="">
						<div>
							<span style="color: #0150a1; cursor: pointer;">Lite buy</span>
						</div>
						<div>
							<span style="color: #f38787;"><span>04.01.2019</span> (1 день)</span>
							<span style="color: #7b7d81;"> для <span>Садвокасов Данияр</span></span> 
							<span style="font-weight: bold;"> Связаться с клиентом</span>
						</div>
						<div style="width: 100%;">
							<form @submit.prevent>
								<input type="text" placeholder="Добавить результат" style="height: 38px; font-size: 15px; padding-left: 10px; outline: none; width: 80%;" required>
								<input class="btn" type="submit" value="Выполнить" style="width: 110px; height: 38px;">
							</form>
						</div>
					</div>
				</div>
			</div>
		</transition>
		<div class="header">
			<div class="about r-border child">
				<div class="table_type table_type__vertical">
					<div class="first_block block"></div>
					<div class="second_block block"></div>
					<div class="third_block block"></div>
				</div>
				<div class="table_type table_type__horrizontal table_type__activate">
					<div class="first_block block"></div>
					<div class="second_block block"></div>
					<div class="third_block block"></div>
				</div>
			</div>

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
			</div>

			<div class="search r-border child">
				<svg class="list-top-search__icon svg-icon svg-common--filter-search-dims">
					<use xlink:href="#common--filter-search">
						<svg viewBox="0 0 16 15" id="common--filter-search" width="100%" height="100%"><path id="chSearch" class="chcls-1" d="M6.493 12.994a6.5 6.5 0 1 1 6.5-6.5 6.5 6.5 0 0 1-6.5 6.5zm0-11.007a4.506 4.506 0 1 0 4.5 4.506 4.5 4.5 0 0 0-4.5-4.506zM16.01 14.11l-.894.9-3.108-2.632 1.38-1.388z"></path></svg>		
					</use>
				</svg>
				<input type="text" placeholder="Фильтр" class="input">
				<!-- <span class="deals">
					<span class="count">559 сделок: </span>
					<span class="value">504 196 400 тг</span>
				</span> -->
			</div>

			<div class="setings child">
				<svg class="svg-icon svg-controls--button-more-dims">
					<use xlink:href="#controls--button-more">
						<svg viewBox="0 0 13 3" id="controls--button-more" width="100%" height="100%"><path id="dymore" class="dycls-1" d="M1.5 0A1.5 1.5 0 1 1 0 1.5 1.5 1.5 0 0 1 1.5 0zm5 0A1.5 1.5 0 1 1 5 1.5 1.5 1.5 0 0 1 6.5 0zm5 0A1.5 1.5 0 1 1 10 1.5 1.5 1.5 0 0 1 11.5 0z"></path></svg>		
					</use>
				</svg>
				<button class="button__setings">Синхронизировать</button>		
				<button class="button__new_deal">
					<svg class="svg-icon svg-controls--button-add-dims">
						<use xlink:href="#controls--button-add">
							<svg viewBox="0 0 9 9" id="controls--button-add" width="100%" height="100%"><path id="dv_" data-name="+" class="dvcls-1" d="M9 5H5v4H4V5H0V4h4V0h1v4h4v1z"></path></svg>		
						</use>
					</svg>
					Добавить задачу
				</button>
			</div>
		</div>
		<div class="body">
			<table>
				<thead>
					<tr style="border-top: none;">
						<th><input type="checkbox">Дата исполнения / Отв.</th>
						<th>Контакт или сделка</th>
						<th style="border-right: none">Текст задачи</th>
					</tr>
				</thead>
				<tbody>
					<tr class="groupName">
						<td>Просроченные задачи</td>
					</tr>
					<tr class="task" @click="show_modal=true">
						<td>
							<div><input type="checkbox" v-on:click.stop=""></div>
							<div class="info">
								<span>04.01.2019 23:59</span>
								<span>Садвокасов Данияр</span>
							</div>
						</td>
						<td>
							<div class="info">
								<span>Lite buy</span>
								<span>Lite buy, Lite buy</span>
							</div>
						</td>
						<td>
							<span class="info">Связаться с клиентом</span>
						</td>
					</tr>
					<tr class="groupName">
						<td>Задачи на сегодня</td>
					</tr>
					<tr class="task">
						<td>
							<div><input type="checkbox"></div>
							<div class="info">
								<span>04.01.2019 23:59</span>
								<span>Садвокасов Данияр</span>
							</div>
						</td>
						<td>
							<div class="info">
								<span>Lite buy</span>
								<span>Lite buy, Lite buy</span>
							</div>
						</td>
						<td>
							<span class="info">Связаться с клиентом</span>
						</td>
					</tr>
					<tr class="groupName">
						<td>Задачи на завтра</td>
					</tr>
					<tr class="task">
						<td>
							<input type="checkbox">
							<div class="info">
								<span>04.01.2019 23:59</span>
								<span>Садвокасов Данияр</span>
							</div>
						</td>
						<td>
							<div class="info">
								<span>Lite buy</span>
								<span>Lite buy, Lite buy</span>
							</div>
						</td>
						<td>
							<span class="info">Связаться с клиентом</span>
						</td>
					</tr>
					<tr class="groupName">
						<td>Будущие задачи</td>
					</tr>
					<tr class="task">
						<td>
							<input type="checkbox">
							<div class="info">
								<span>04.01.2019 23:59</span>
								<span>Садвокасов Данияр</span>
							</div>
						</td>
						<td>
							<div class="info">
								<span>Lite buy</span>
								<span>Lite buy, Lite buy</span>
							</div>
						</td>
						<td>
							<span class="info">Связаться с клиентом</span>
						</td>
					</tr>
				</tbody>
			</table>
		</div>
	</div>
</template>

<script>

export default {
	data(){
		return {
			show_modal: false
		}
	},
	methods: {
		
	},
  components: {
  },
  mounted(){
		// document.querySelector('.modal_body').addEventListener("click",(event) => event.stopPropagation());
	}
}
</script>

<style scoped>
/*header*/
	.content{
		height: 100vh;
		width: 100%;
		background-color: #f5f5f5;
		position: relative;
		width: calc(100% - 70px);
		background-color: #fff;
		position: absolute;
		left: 70px;
	}
	.header{
		height: 64px;
		display: flex;
		flex-direction: row;
		border-bottom: 1px solid rgba(0,0,0,0.1);
		background-color: #ffffff;
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
		font-weight: 600;
		font-size: 0.95em;
		margin-right: 20px;
		white-space: nowrap;
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
		width: 100%;
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
		width: 33%;
		border-right: #e5e5e5 solid 1px;
		border-bottom: #e5e5e5 solid 1px;
		font-size: 13px;
		text-align: left;
		padding-left: 10px;
	}

	tr {
		border-top: #e5e5e5 solid 1px;
		border-bottom: #e5e5e5 solid 1px;;
		width: 100%;
	}

	tr:hover {
		background-color: #f8faff;
	}

	td {
		padding: 10px;
	}

	td:first-child,th:first-child {
		padding-left: 50px;
	}

	table input {
		position: absolute;
		height: 20px;
		transform: scale(1.7);	
		left: 30px;
	}

	td input {
		height: 40px;
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

	.groupName:hover {
		background-color: #fff;
	}

	.task {
		height: 65px;
	}

	.info {
		display: flex;
		flex-direction: column;
		color: #7a7f85
	}

	/*modal*/
	.fade-enter-active, .fade-leave-active {
		transition: opacity .5s;
	}
	.fade-enter, .fade-leave-to /* .fade-leave-active до версии 2.1.8 */ {
		opacity: 0;
	}

	.modal {
		z-index: 99;
		position: absolute;
		width: 100%;
		height: 100%;
	}

	.modal_main {
		height: 100%;
		width: 100%;
		background-color: rgba(255, 255, 255, .7);
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.modal_body {
		width: 710px;
		height: 170px;
		background-color: #f5f5f5;
		position: absolute;
		border: 1px solid #d3d6d7;
		box-shadow: 0 14px 24px 1px rgba(0,0,0,.1);
			webkit-transition: opacity .1s,-webkit-transform .3s;
    		transition: transform .3s,opacity .1s;
    		transition: transform .3s,opacity .1s,-webkit-transform .3s;
    	border-radius: 1px;
    	z-index: 999;
    	padding: 30px;
    	display: flex;
    	flex-direction: column;
    	justify-content: space-between;
	}

	.btn {
	margin-left: 10px;
    padding: 0 20px;
    text-transform: none;
    color: #fff;
    height: 38px;
    background-color: #c7c9ce;
    border-color: #c7c9ce;
	}
</style>