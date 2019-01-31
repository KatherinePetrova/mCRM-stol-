<template>
	<div class="right_ponel">
			
			<div class="about">
				<div class="head">
					<div class="lead_name">
						<input type="text" spellcheck=false placeholder="Сделка #XXXXXX" >
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
						<div class="section" style="font-size: 0.9em">
							<span v-for="item, index in vklads" :class="{active: selected_vklad==index}" @click="selected_vklad=index">{{item.name}}</span>
						</div>
						<button class="dots">
							<div class="dot"></div>
							<div class="dot"></div>
							<div class="dot"></div>
						</button>
					</div>
				</div>

				<div class="body">
					<div class="input" v-for="item in vklads[selected_vklad].stroks">
						<div class="child">
							<span class="name">{{item.name}}</span>
						</div>
						<div class="child">
							<input class="text" type="text" :value="item.value">
						</div>
					</div>
					<div class="child" style="border-bottom: 1px solid #62757d; margin: 15px 0" v-if="selected_vklad==0"></div>
					<div class="contact" v-if="selected_vklad==0">
						<div class="img"></div>
						<input type="text" value="Нуруллаев Мансур">
						<button class="dots">
							<div class="dot"></div>
							<div class="dot"></div>
							<div class="dot"></div>
						</button>
					</div>
					<div class="input" v-for="item in vklads[selected_vklad].stroks" v-if="selected_vklad==0">
						<div class="child">
							<span class="name">{{item.name}}</span>
						</div>
						<div class="child">
							<input class="text" type="text" :value="item.value" >
						</div>
					</div>
					<div class="input" v-for="item in vklads[selected_vklad].stroks" v-if="selected_vklad==0">
						<div class="child">
							<span class="name">{{item.name}}</span>
						</div>
						<div class="child">
							<input class="text" type="text" :value="item.value">
						</div>
					</div>
				</div>
			</div>
			
			<div class="chat">
				
			</div>
			
			<div class="widget">
				
			</div>
			
		</div>
</template>

<script type="text/javascript">
import axios from "axios";
  export default{
	props: ['id'],
	async mounted(){
		console.log(this.id);
		try{
			var lead = await axios('http://crm.aziaimport.kz:3000/api/where/leads/0', {
				method: 'post',
				data: {where: {id: 2235}, orderby: 'created_at'},
				withCredentials: true
			});
			console.log(lead)
		} catch(e){

		}
	},
  	data(){
  		return{
			lead: {},
  			nony: false,
  			select_task: '',
  			selected_vklad: 0,
  			vklads: [
  				{
  					name: 'Основное',
  					stroks: [
  						{
  							name: 'Ответственный',
  							value: 'Садвокасов Данияр'
  						},
  						{
  							name: 'Бюджет',
  							value: '5000'
  						},
  						{
  							name: 'Курс рубля в счете на оплату',
  							value: '5.7'
  						},
  						{
  							name: '№ счета РК',
  							value: '548944123'
  						},
  						{
  							name: 'Процент',
  							value: '7'
  						},
  						{
  							name: 'Создатель сделки',
  							value: 'Садвокасов Данияр'
  						}
  					]

  				},
  				{
  					name: 'Доп. информация',
  					stroks: [
  						{
  							name: 'кек',
  							value: 'Садвокасов Данияр'
  						},
  						{
  							name: 'хуек',
  							value: '5000'
  						},
  						{
  							name: 'Курс рубля в счете на оплату',
  							value: '5.7'
  						},
  						{
  							name: '№ счета РК',
  							value: '548944123'
  						},
  						{
  							name: 'Процент',
  							value: '7'
  						},
  						{
  							name: 'Создатель сделки',
  							value: 'Садвокасов Данияр'
  						}
  					]

  				}
  			],
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
	  

  }
</script>

<style scoped>
	::-webkit-scrollbar {
	width: 5px;
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

/*card*/

	.right_ponel {
		position: absolute;
		left: 70px;
		width: calc(100% - 70px);
		height: 100vh;
		display: flex;
	}

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
		min-width: 40em;
	}
	/*r-head*/
		.right_ponel>.about>.head{
			display: flex;
			padding: 1em 1.5em 0;
			min-height: 11em;
			max-height: 11em;
			flex-direction: column;
			background-color: #203d49;
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
</style>