<template>
	<div class="content">
		<div class="info_panel"></div>
		<div class="main_mail"><div class="header">
			<div class="about child">
				<div class="table_type table_type__horrizontal">
					<div class="first_block block"></div>
					<div class="second_block block"></div>
					<div class="third_block block"></div>
				</div>
				<span class="about-name">Входящие</span>
			</div>
			<div class="setings child">
				<button class="button__new_deal">
					<svg class="svg-icon svg-controls--button-more-dims">
						<use xlink:href="#controls--button-more">
							<svg viewBox="0 0 13 3" id="controls--button-more" width="100%" height="100%"><path id="dymore" class="dycls-1" d="M1.5 0A1.5 1.5 0 1 1 0 1.5 1.5 1.5 0 0 1 1.5 0zm5 0A1.5 1.5 0 1 1 5 1.5 1.5 1.5 0 0 1 6.5 0zm5 0A1.5 1.5 0 1 1 10 1.5 1.5 1.5 0 0 1 11.5 0z"></path></svg>		
						</use>
					</svg>
					<span style="margin-left: 7px;">Еще</span>
				</button>
			</div>
		</div>
	</div>
		
		<div class="body">
			<table>
				<thead>
					<tr style="border-top: none;">
						<th style="width: 290px;"><input type="checkbox">от</th>
						<th style="width: 505px;">Тема</th>
						<th style="width: 255px;">Сделка/покупатель</th>
						<th style="border-right: none; width: 180px;">Дата</th>
					</tr>
				</thead>
				<tbody>
					<tr class="task">
						<td>
							<div><input type="checkbox"></div>
							<div class="info">
								<span>Azia Import</span>
							</div>
						</td>
						<td>
							<div class="info letter">
							<span class="point">&bull;</span>
							<span class="notif">Садвокасов Данияр, у вас новое уведомление</span>
							</div>
						</td>
					</tr>
				</tbody>
			</table>
		</div>
	</div>
</template>

<script>

export default {
  components: {
  },
  data(){
	  return {
		  dfld: [
			  
		  ]
	  }
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
		width: calc(100%-70px);
		left: 70px;
		position: absolute;
	}
	.header{
		height: 64px;
		display: flex;
		flex-direction: row;
		background-color: #f5f5f5;
		justify-content: space-between;
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
		line-height: 21px;
		margin-right: 20px;
		margin-left: 10px;
		font-size: 1.5em;
	}
	.table_type{
		height: 100%; 
		display: flex;
		margin: 2.5px 5px;
		cursor: pointer;
	}
	.table_type__horrizontal{
		flex-direction: column;
		height: 100%;
		justify-content: space-between;
	}
	.table_type.table_type__activate>.block{
		background-color: #4c8bf7;
	}
	.table_type>.block{
		background-color: rgba(0,0,0);
		width: 10px;
		margin: 0 2px;
		height: 100%;
		display: block;
	}
	.table_type__horrizontal>.block{
		width: 20px;
		margin: 0;
		height: 3px;
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
		width: 700px;
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
		font-weight: 700;
		padding: 0 0.5em;
		float: right;
	}
	.button__setings{
		border: 1px solid #dbdedf;
		color: #313942;
		background-color: #fcfcfc;
	}
	.button__new_deal{
		border: 1px solid #dbdedf;
		background-color: #fcfcfc;
		color: #2e3640;
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
		padding: 25px;
		color: #7a7f85;
	}
	table {
		width: 100%;
		border-collapse: collapse;
		background-color: #ffffff;
	}

	

	thead {
		color: #b9c0cb;
		text-transform: uppercase;
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
		height: 40px;
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
		color: #7a7f85;
	}

	.letter{
		color: #0057a9;
		display: flex;
		flex-direction: row;
		height: 40px;
	}

	.point {
		color: #008ed5;
		/*position: absolute;
		left: 10px;
		top: 3px;*/
		font-size: 45px;
		cursor: pointer;
		display: flex;
		align-items: center;
		justify-content: center;
		height: 100%;
		width: 12px;
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

	.notif {
		line-height: 40px;
		margin-left: 20px;
	}
</style>