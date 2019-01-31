<template>
	<div class="main">
    	<lpanel :chose="1"></lpanel>
    	<div class="loading">
    		<div></div>
    	</div>
   	</div>
</template>

<script>
import axios from 'axios'
import lpanel from '~/components/lpanel.vue';

export default {
    
    components: {lpanel},

    mounted(){

		axios('http://crm.aziaimport.kz:3000/leads/select/pipelines', {
			method: 'post',
			withCredentials: true
		}).then((res)=>{
			for(var i=0; i<res.data.length; i++){
				if(res.data[i].is_main==1){
					this.$router.push(`/leads/${res.data[i].id}`);
				}
			}
		});
    },
}
</script>

<style scoped>
html, body {
    margin: 0;
    padding: 0;
}

.main {
  background-color: rgba(240, 240, 240);
  display: flex;
  width: 100vw;
  position: relative;
  min-height: 100vh;
  position: absolute;
  flex-direction: row;
}

.loading {
	display: flex;
	justify-content: center;
	align-items: center;

	position: absolute;

	min-height: 100vh;
	min-width: calc(100%-70px);

	left: 70px;

	border-width: 20px;
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
</style>