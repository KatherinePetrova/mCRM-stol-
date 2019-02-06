<template>
	<div class="content">
		<div class="header">
			<div class="about r-border child">
				<select class="about-name" style="cursor: pointer" @change="changePip">
					<option v-for="item in pipeline" :value="item.id" :selected="item.id==id">{{item.name}}</option>	
				</select>
			</div>

			<div class="search r-border child">
				<svg class="list-top-search__icon svg-icon svg-common--filter-search-dims">
					<use xlink:href="#common--filter-search">
						<svg viewBox="0 0 16 15" id="common--filter-search" width="100%" height="100%"><path id="chSearch" class="chcls-1" d="M6.493 12.994a6.5 6.5 0 1 1 6.5-6.5 6.5 6.5 0 0 1-6.5 6.5zm0-11.007a4.506 4.506 0 1 0 4.5 4.506 4.5 4.5 0 0 0-4.5-4.506zM16.01 14.11l-.894.9-3.108-2.632 1.38-1.388z"></path></svg>		
					</use>
				</svg>
				<input type="text" placeholder="Поиск и фильтр" class="input">
				<span class="deals">
					<span class="count"></span>
					<span class="value"></span>
				</span>
			</div>

			<div class="setings child" onscroll="">
				<svg class="svg-icon svg-controls--button-more-dims">
					<use xlink:href="#controls--button-more">
						<svg viewBox="0 0 13 3" id="controls--button-more" width="100%" height="100%"><path id="dymore" class="dycls-1" d="M1.5 0A1.5 1.5 0 1 1 0 1.5 1.5 1.5 0 0 1 1.5 0zm5 0A1.5 1.5 0 1 1 5 1.5 1.5 1.5 0 0 1 6.5 0zm5 0A1.5 1.5 0 1 1 10 1.5 1.5 1.5 0 0 1 11.5 0z"></path></svg>		
					</use>
				</svg>
				<button class="button__setings">Настроить</button>		
				<nuxt-link class="button__new_deal" to="/leads/single">
					<svg class="svg-icon svg-controls--button-add-dims">
						<use xlink:href="#controls--button-add">
							<svg viewBox="0 0 9 9" id="controls--button-add" width="100%" height="100%"><path id="dv_" data-name="+" class="dvcls-1" d="M9 5H5v4H4V5H0V4h4V0h1v4h4v1z"></path></svg>		
						</use>
					</svg>
					Новая сделка
				</nuxt-link>
			</div>
		</div>

		

		<div class="about_today">
			
		</div>
		<div class="body">

			<div class="group" v-for="(item, index) in groups" :key="index">
				<div class="title">
					<span class="name">{{item.name}}</span>
					<span class="count">1425 сделок, 524 000тг</span>
				</div>
				<Container :group-name="index == 0 ? '' : 'unzero'" :id="item.id" class="tasks" @drop='e=> onDrop(index, e)' @scroll="scroll(e)" :get-child-payload="getCardPayload(item.id)">
					<Draggable class="task" v-for="(lead, key) in item.leads" :key="key" style="min-height: 5rem; cursor: move">
						<div class="head">
							<div class="names">
								<span class="name__first">{{loh(lead.contact.name)}}</span>
								<span class="name__second" :title="lead.company.name" style="text-overflow: ellipsis">, {{loh(lead.company.name)}}</span>
							</div>
							<span class="date">{{date(lead.created_at)}}</span>
						</div>
						<div class="body">
							<nuxt-link :to="'/leads/single/' + lead.id">{{lead.name}}</nuxt-link>
						</div>
					</Draggable>
				</Container>
			</div>

		</div>
	</div>
</template>
<script>
  import { Container, Draggable } from "vue-smooth-dnd";
  export default{
	components: { Container, Draggable },
	props: ['id', 'pipeline', 'groups'],
	mounted(){
		
	},
  	methods: {
		loh(data){
			if(data=='loh_company' || data=='loh_contact'){
				return 'Неизвестнo'
			} else {
				return data
			}
		},
		date(e){
			return `${e.split('T')[0]} ${e.split('T')[1].split('.')[0]}`
		},
		scroll(e){
			console.log(e);
		},
		changePip(el){
			this.$router.push(`/leads/${el.target.value}`)
		},
  		onDrop(dropResult, e){
			  if(e.removedIndex !== null && e.addedIndex !== null){
				this.groups[dropResult].leads.splice(e.removedIndex, 1);
				this.groups[dropResult].leads.splice(e.addedIndex, 0, e.payload); 
				return;
			  }
			  if(e.removedIndex !== null) this.groups[dropResult].leads.splice(e.removedIndex, 1)
			  else if(e.addedIndex !== null) this.groups[dropResult].leads.splice(e.addedIndex, 0, e.payload)
				this.groups = this.groups;
  			},
  		getCardPayload (columnId) {
  			return index => {
				  console.log(this.groups.filter(p => p.id === columnId)[0].leads[index])
  				return this.groups.filter(p => p.id === columnId)[0].leads[index];
  			}
  		},
  		widthInput(element){
  			var len = element.target.value.split('').length;
  			element.target.style.width = len * 5 * (1 + len/50) + 20 + 'px'
  		}
  	}
  }
</script>
<style scoped>
::-webkit-scrollbar {
	width: 1px;
}
::-webkit-scrollbar-track {
	background: #f1f1f1; 
}
::-webkit-scrollbar-thumb {
	background: #888; 
}
::-webkit-scrollbar-thumb:hover {
	background: #555; 
}


input[type=number]::-webkit-inner-spin-button, 
input[type=number]::-webkit-outer-spin-button { 
  -webkit-appearance: none; 
  margin: 0; 
}


	button, a, input{
		outline: none;
		cursor: pointer;
	}
	.circle{
		display: flex;
		height: 5px;
		width: 5px;
		margin: 2.5px;
		border-radius: 50%;
		border: none;
		background-color: rgba(0,0,0,0.2);
	}
	.yellow{
		background-color: #e4b248;	
	}
	.content{
		height: 100vh;
		width: calc(100% - 70px);
		position: absolute;
		left: 70px;
		background-color: #fff;
	}
	.header{
		height: 64px;
		display: flex;
		flex-direction: row;
		border-bottom: 1px solid rgba(0,0,0,0.1);
	}
	.r-border{
		border-right: 1px solid rgba(0,0,0,0.1);
	}
	.header>.child{
		display: flex;
		height: 100%;
		padding: 0.5em 1.75em;
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

		height: 100%;

		border: none;
		outline: none;
	}

	.about-name>option {
		padding: 100px 20px;
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
		height: 50%;
	}
	.table_type__vertical>.second_block{
		height: 35%;	
	}
	.table_type__vertical>.third_block{
		height: 20%;
	}

	.search>svg{
		width: 20px;
		fill: #6e747a;
	}
	.search>.input{
		border: none;
		outline: none;
		font-size: 100%;
		width: 450px;
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

		font-size: 0.75em;

		text-decoration: none;

	}
	.button__new_deal>svg{
		width: 20px;
		height: 25%;
	}
/*card*/
	.dots{
		background-color: transparent;
		border: none;
		display: flex;
		flex-direction: row;
	}
	.dots>.dot{
		background-color: #fff;
		height: 3px;
		width: 3px;
		margin: 0 1px;
		border-radius: 50%;
	}
	.content>.right_ponel{
		width: 95vw;
		height: 100%;
		top: 0;
		z-index: 10;
		background-color: #fed;
		position: absolute;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}
	.right_ponel>.about, .right_ponel>.chat, .right_ponel>.widget{
		width: 47.5%;
		display: flex;
		height: 100%
	}
	.right_ponel>.about{
		background-color: #fff;
		display: flex;
		flex-direction: column;
		position: relative;
	}
	/*r-head*/
		.right_ponel>.about>.head{
			display: flex;
			padding: 1em 1.5em 0;
			min-height: 11em;
			max-height: 11em;
			flex-direction: column;
		}
		.right_ponel>.about>.head>.lead_name{
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			padding-bottom: 0.5em;
		}
		.right_ponel>.about>.head input{
			background-color: transparent;
			border: none;
			width: calc(100% - 27px);
			font-size: 1.25em;
			color: #fff;
			outline: none;
		}
		.right_ponel>.about>.head input:focus{
			border-bottom: 1px solid #4c8bf7;
		}
		.right_ponel>.about>.head>.block_tags{
			width: 100%;
			display: flex;
			flex-wrap: wrap;
			cursor: pointer;
		}
		.right_ponel>.about>.head>.block_tags>input{
			width: 100%;
		}
		.right_ponel>.about>.head>.block_tags>.tags{
			display: flex;
			flex-wrap: wrap;
			width: 100%;
			color: #fff;
			padding: 0;
			flex-direction: row;
		}
		.right_ponel>.about>.head>.block_tags>.tags>.tag{
			list-style-type: none;
			background-color: rgba(56,82,93,0.5);
			padding: 0 7px;
			height: 21px;
			display: flex;
			align-items: center;
			border: 1px solid #38525d;
			white-space: nowrap;
		}
		.right_ponel>.about>.head>.steps{
			display: flex;
			flex-direction: column;
			font-size: 0.9em;
		}
		.right_ponel>.about>.head>.steps>.title{
			color: #617480;
		}
		.right_ponel>.about>.head>.steps>.name{
			color: #fff;
			cursor: pointer;
		}
		.right_ponel>.about>.head>.steps>.strip{
			width: 100%;
			height: 2px;
			background-color: #00000059;
		}
		.right_ponel>.about>.head>.steps>.strip>.strip_color{
			width: 33.33%;
			height: 100%;
		}
		.right_ponel>.about>.head>.settings{
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			bottom: 0;
			width: 100%;
		}
		.right_ponel>.about>.head>.settings>.section{
			color: #62757d;
			display: flex;
			width: 100%;
		}
		.right_ponel>.about>.head>.settings>.section>.active{
			color: #fff;
			border-bottom: 2.5px solid #fff;
			padding-bottom: 0;
		}
		.right_ponel>.about>.head>.settings>.section>span{
			width: 100%;
	    	min-width: 75px;
	    	overflow: hidden;
	    	cursor: pointer;
	    	padding: 5px 2px;
	    	text-align: center;
	    	word-wrap: break-word;
	    	white-space: nowrap;
		}

	/*r-body*/
		.right_ponel>.about>.body{
			padding: 1em 1.5em 0;
			color: #848c90;
			font-size: 1em;
			overflow-y: auto;
			padding-bottom: 100px;
		}
		.right_ponel>.about>.body>.input{
			width: 100%;
			display: flex;
			justify-content: space-between;
			padding: 5px 0;
		}
		.right_ponel>.about>.body>.input>.child{
			width: 50%;
			display: flex;
			justify-content: flex-start;
		}
		.right_ponel>.about>.body>.input>.child>.text{
			border: none;
			background-color: transparent;
		}
		.right_ponel>.about>.body>.input>.child>.text:focus{
			border-bottom: 1px solid #4c8bf7;
		}
		.right_ponel>.about>.body>.input>.child>.doesn_t{
			color: #000;
		}
		.right_ponel>.about>.body>.input>.child>.select{
			position: relative;
			width: 100%;
		}
		.right_ponel>.about>.body>.input>.child>.select>button{
			border: none;
			background-color: transparent;
			display: flex;
			flex-direction: row;
			align-items: center;
			width: 100%;
		}
		.right_ponel>.about>.body>.input>.child>.select>button:focus{
			border-bottom: 1px solid #4c8bf7;
		}
		.right_ponel>.about>.body>.input>.child>.select>button>.sqr{
			right: -3.5px;
			margin: -1px 4px 0;
			height: 6px;
			width: 6px;
			border: 0px;
			border-bottom: 1px;
			border-right: 1px;
			border-style: solid;
			border-color: #000;
			transform: rotate(45deg);
		}
		.right_ponel>.about>.body>.input>.child>.select>.block_options{
			position: absolute;
			border: 1px solid #848c90;
			/*width: 100%;*/
			display: flex;
			flex-direction: column;
			align-items: center;
			background-color: #fff;
			/*opacity: 0;*/
		}
		.right_ponel>.about>.body>.input>.child>.select>.block_options>.option{
			border-bottom: 1px solid #848c90;
			width: 100%;
			cursor: pointer;
			display: flex;
			justify-content: center;
			text-align: center;
		}
		.right_ponel>.about>.body>.contact{
			display: flex;
			width: 100%;
			position: relative;
			align-items: center;
		}
		.right_ponel>.about>.body>.contact input{
			background-color: transparent;
			border: none;
			width: calc(70% - 60px);
			font-size: 1.25em;
			font-weight: 600;
			outline: none;
			position: absolute;
			left: 60px;
		}
		.right_ponel>.about>.body>.contact input:focus{
			border-bottom: 1px solid #4c8bf7;
		}
		.right_ponel>.about>.body>.contact>.img{
			display: flex;
			height: 50px;
			width: 50px;
			background-image: url('/avatar.jpg');
			background-size: cover;
			background-position: center;

			border-radius: 50%;

			margin-right: 10px;

		}


/*
								<div class="select">
									<span>Выбран</span>
									<div class="sqr"></div>
									<div class="block_otions">
										<div class="option">Выбрать</div>
										<div class="option">Выбрать</div>
										<div class="option">Выбрать</div>
									</div>
								</div>*/












	.right_ponel>.chat{
		background-color: #fee;
	}
	.right_ponel>.widget{
		width: 5%;
		background-color: #ddf;
	}
	.right_ponel>.about>.head{
		width: 100%;
		display: flex;
		background-color: #263d4c;
		height: 12em;
	}
/*body*/
	.content>.body{
		height: calc(100% - 64px);
		width: auto;
		overflow-x: scroll;
		padding-left: 30px;
		background-color: #f5f5f5;
		display: flex;
		flex-direction: row;
	}
	.body>.group{
		overflow: hidden;
		height: 100%;
		width: 332px;
		min-width: 20rem;
		padding-right: 20px;
	}
	.group>.title{
		height: 50px;
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		padding: 12.5px 0 5px;
		border-bottom: 2px solid #313942;
		color: #313942;
		font-size: 0.8em;

		white-space: nowrap;
		text-overflow: ellipsis;

	}
	.group>.title.new{
		color: #626262;
		border-bottom: 2px solid #626262;
	}
	.title>.name{
		text-transform: uppercase;
		font-weight: 700;
	}
	.title>.count{
	}

	.group>.tasks{
		height: calc(100% - 50px);
		overflow-y: auto;
		display: flex;
		align-items: center;
		flex-direction: column;
	}
	.tasks>.task{
		margin: 5px 0;
		border: 1px solid rgba(0,0,0,0.2);
		border-radius: 3px; 
		padding: 6px 8px 5px;
		background-color: #fff;
		width: 100%;
	}
	.task>.head{
		/*background-color: #fef;*/
		width: 100%;
		display: flex;
		flex-direction: row;
		font-size: 0.85em;
		justify-content: space-between;
	}
	.task>.head>.names{
		display: flex;
		flex-direction: row;
		text-overflow: ellipsis;
		white-space: nowrap;
		width: 50%;
		overflow: hidden;
	}
	.head>.names>.name__first{
		color: #363b44;
	}
	.head>.names>.name__second{
		color: #626262;
		text-overflow: ellipsis;
		overflow: hidden;
	}
	.task>.head>.date{
		color: #626262;	
	}
	.task>.body{
		margin: 0.4em 0;
	}
	.task>.body>.deal_name{
		font-size: 0.8em;
		color: #0057a9;
	}
	.task>.foot{
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		font-size: 0.75em;	
	}
	.task>.foot>.foot-child{
		display: flex;
		flex-direction: row;
		align-items: center;
	}
	.foot>.foot-child>.value{
		color: #626262;	
	}
	.foot>.foot-child>.have_task{
		color: #e4b248;
	}
</style>