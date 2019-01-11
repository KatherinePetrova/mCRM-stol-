<template>
	<div class="content">
		<div class="header">
			<div class="about r-border child">
				<span class="about-name">Отдел сервиса РК</span>

				<div class="table_type table_type__vertical table_type__activate">
					<div class="first_block block"></div>
					<div class="second_block block"></div>
					<div class="third_block block"></div>
				</div>
				<div class="table_type table_type__horrizontal">
					<div class="first_block block"></div>
					<div class="second_block block"></div>
					<div class="third_block block"></div>
				</div>

			</div>

			<div class="search r-border child">
				<svg class="list-top-search__icon svg-icon svg-common--filter-search-dims">
					<use xlink:href="#common--filter-search">
						<svg viewBox="0 0 16 15" id="common--filter-search" width="100%" height="100%"><path id="chSearch" class="chcls-1" d="M6.493 12.994a6.5 6.5 0 1 1 6.5-6.5 6.5 6.5 0 0 1-6.5 6.5zm0-11.007a4.506 4.506 0 1 0 4.5 4.506 4.5 4.5 0 0 0-4.5-4.506zM16.01 14.11l-.894.9-3.108-2.632 1.38-1.388z"></path></svg>		
					</use>
				</svg>
				<input type="text" placeholder="Поиск и фильтр" class="input">
				<span class="deals">
					<span class="count">559 сделок: </span>
					<span class="value">504 196 400 тг</span>
				</span>
			</div>

			<div class="setings child">
				<svg class="svg-icon svg-controls--button-more-dims">
					<use xlink:href="#controls--button-more">
						<svg viewBox="0 0 13 3" id="controls--button-more" width="100%" height="100%"><path id="dymore" class="dycls-1" d="M1.5 0A1.5 1.5 0 1 1 0 1.5 1.5 1.5 0 0 1 1.5 0zm5 0A1.5 1.5 0 1 1 5 1.5 1.5 1.5 0 0 1 6.5 0zm5 0A1.5 1.5 0 1 1 10 1.5 1.5 1.5 0 0 1 11.5 0z"></path></svg>		
					</use>
				</svg>
				<button class="button__setings">Настроить</button>		
				<button class="button__new_deal">
					<svg class="svg-icon svg-controls--button-add-dims">
						<use xlink:href="#controls--button-add">
							<svg viewBox="0 0 9 9" id="controls--button-add" width="100%" height="100%"><path id="dv_" data-name="+" class="dvcls-1" d="M9 5H5v4H4V5H0V4h4V0h1v4h4v1z"></path></svg>		
						</use>
					</svg>
					Новая сделка
				</button>
			</div>
		</div>

		<div class="about_today">
			
		</div>
		<div class="body">

			<div class="group" v-for="(group, group_id) in groups" :key="group_id">
				<div class="title" :class="!group.id ? 'new' : ''">
					<span class="name">{{group.name}}</span>
					<span class="count">{{!group.id ? 'Заявок: ' + group.count : group.count + ' сделок: ' + group.money + 'тг'}}</span>
				</div>

				<Container class="tasks" :id="group.id" :group-name="group.id == 0 ? '' : 'unzero'" 
									 @drop="e=> onDrop(group_id,e)"
									 :get-child-payload="getCardPayload(group.id)">

					<Draggable class="task" :id="task.id" v-for="(task, task_id) in group.tasks" :key="task_id">
						<div class="head">
							<div class="names">
								<span class="name__first">{{task.people}} , </span>
								<span class="name__second">{{task.fabriс}}</span>
							</div>
							<span class="date">{{task.date}}</span>
						</div>
						<div class="body">
							<div class="deal_name">{{task.deal}}</div>
						</div>
						<div class="foot">
							<div class="foot-child">
								<span class="value">{{task.value}} тг</span>
								<div class="circle grey"></div>
							</div>
							<div class="foot-child">
								<span class="have_task">{{task.have}}</span>
								<div class="circle yellow"></div>
							</div>
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
  	data(){
  		return{
  			select_task: '',
  			groups:[
  			{
  				name: 'Неразобранное',
  				count: 0,
  				id: 0,
  				tasks:[]
  			},
  			{
  				name: 'Новая заявка',
  				count: 3,
  				money: 9698156,
  				id: 1,
  				tasks:[
  				{
  					people: 'Нурман',
  					fabriс: 'КемалханСтройЭл',
  					date: '04.01.2019',
  					deal: 'ФАКТОР ГРУПП №18/2812-02 от 28.12.18г.',
  					value: 1088442,
  					have: 0,
  					id: 0
  				},
  				{
  					people: 'Нурман',
  					fabriс: 'КемалханСтройЭл',
  					date: '04.01.2019',
  					deal: 'ФАКТОР ГРУПП №18/2812-02 от 28.12.18г.',
  					value: 1088442,
  					have: 1,
  					id: 1
  				},
  				{
  					people: 'Нурман',
  					fabriс: 'КемалханСтройЭл',
  					date: '04.01.2019',
  					deal: 'ФАКТОР ГРУПП №18/2812-02 от 28.12.18г.',
  					value: 1088442,
  					have: 2,
  					id: 2
  				},
  				]
  			},
  			{
  				name: 'Получить с с/о рф',
  				count: 1,
  				money: 1088442,
  				id: 3,
  				tasks:[
  				{
  					people: 'Нурман',
  					fabriс: 'КемалханСтройЭл',
  					date: '04.01.2019',
  					deal: 'ФАКТОР ГРУПП №18/2812-02 от 28.12.18г.',
  					value: 1088442,
  					have: 0,
  					id: 3
  				},
  				]
  			},

  			],
  		}
  	},
	  methods: {
	    onDrop(dropResult, e){
	      if(e.removedIndex !== null) this.groups[dropResult].tasks.splice(e.removedIndex, 1)
	      if(e.addedIndex !== null) this.groups[dropResult].tasks.splice(e.addedIndex, 0, e.payload)
	      
	    },
      getCardPayload (columnId) {
	      return index => {
	        return this.groups.filter(p => p.id === columnId)[0].tasks[index];
	      }
	    },
		}
  }
</script>
<style scoped>
/*main*/
	button, a{
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
/*header*/
	.content{
		margin-left: 65px;
		height: 100vh;
		width: calc(100% - 65px);
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
	}
	.button__new_deal>svg{
		width: 20px;
		height: 25%;
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
		overflow-y: hidden;
		height: 100%;
		width: 332px;
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
	}
	.head>.names>.name__first{
		color: #363b44;
	}
	.head>.names>.name__second{
		color: #626262;
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