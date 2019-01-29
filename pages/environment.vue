<template>
	<div class="main">		<lpanel @chose="chose"></lpanel>
		<lists v-if="selecty==3"></lists>
		<tasks v-if="selecty==2"></tasks>
		<leads v-if="selecty==1"></leads>
	</div>
</template>

<script>
import lpanel from '~/components/lpanel.vue'
import tasks from '~/components/tasks.vue'
import lists from '~/components/lists.vue'
import leads from '~/components/leads.vue'
import sign_in from '~/components/sign_in.vue'
import sign_up from '~/components/sign_up.vue'


export default {
  components: {
    lpanel,
    tasks,
    lists,
    leads,
    sign_up,
    sign_in,
  },
  data(){
  	return {
  		selecty: 0
  	}
  },
  methods: {
  		chose(data){
  			this.selecty = data;
  		}
  }
}
</script>

<style>
	.main {
		background-color: #000;
		display: flex;
		min-width: 100%;
		position: relative;
		min-height: 100vh;
		position: absolute;
		flex-direction: row;
	}
</style>