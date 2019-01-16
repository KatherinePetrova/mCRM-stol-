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

		<div class="right_ponel">
			
			<div class="about">
				<div class="head">
					<div class="lead_name">
						<input type="text" spellcheck=false placeholder="Сделка #XXXXXX">
						<button class="dots">
							<div class="dot"></div>
							<div class="dot"></div>
							<div class="dot"></div>
						</button>
					</div>
					<label class="block_tags" for="new_tag">
						<ul class="tags">
							<li class="tag">#Тестирование</li>
						</ul>
						<input type="text" id="new_tag" spellcheck=false>
					</label>
					<div class="steps">
						<span class="title">Отдел сервиса РК</span>
						<label for="select_strip" class="name">Новая заявка</label>
						<div class="strip">
							<div class="strip_color yellow"></div>
							<div class="strip_color none"></div>
							<div class="strip_color none"></div>
						</div>
						<input type="text" id="select_strip" spellcheck=false>
					</div>
					<div class="settings">
						<div class="section">
							<span class="activ">Основное</span>
							<span class="miss">Доп информация</span>
							<span class="miss">Доставка</span>
							<span class="miss">Счет РФ</span>
							<span class="miss">Аналитика</span>
						</div>
						<button class="dots">
							<div class="dot"></div>
							<div class="dot"></div>
							<div class="dot"></div>
						</button>
					</div>
				</div>

				<div class="body">
					<div class="input">
						<div class="child">
							<span class="name">Отв-ный</span>
						</div>
						<div class="child">
							<input class="text" type="text" value="Садокасов Данияр">
						</div>
					</div>
					<div class="input">
						<div class="child">
							<span class="name">Источник</span>
						</div>
						<div class="child">
								<div class="select">
									<button>
										<span>Выбран</span>
										<div class="sqr"></div>
									</button>
									<div class="block_options">
										<div class="option">Выбрать</div>
										<div class="option">Выбрать</div>
										<div class="option">Выбрать</div>
									</div>
								</div>
						</div>
					</div>
					<div class="input">
						<div class=" child">
							<span class="name">Фото</span>
						</div>
						<div class="child">
							<span class="doesn_t">Не трогать!</span>
						</div>
					</div>
				</div>
			</div>
			
			<div class="chat">
				
			</div>
			
			<div class="widget">
				
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
/*header*/
	.content{
		height: 100vh;
		width: 100%;
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
	}
	/*r-head*/
		.right_ponel>.about>.head{
			display: flex;
			flex-direction: column;
			padding: 1em 1.5em 0;
			justify-content: space-between;
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
		.right_ponel>.about>.head>.settings>.section>.activ{
			color: #fff;
			border-bottom: 3px solid #fff;
		}
		.right_ponel>.about>.head>.settings>.section>span{
			width: 75px;
			margin: 0 0.2em;
			align-items: center;
			white-space: nowrap;
			display: flex;
			flex-wrap: nowrap;
			overflow: hidden;
			cursor: pointer;
		}

	/*r-body*/
		.right_ponel>.about>.body{
			width: 100%;
			display: flex;
			flex-direction: column;
			padding: 1em 1.5em 0;
			color: #848c90;
			font-size: 1.1em;
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