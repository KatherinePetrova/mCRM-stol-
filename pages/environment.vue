<template>
	<div class="main">
<<<<<<< HEAD
		<lpanel></lpanel>
		<!-- <tasks></tasks> -->
		<lists></lists>
		<leads></leads>
=======
		<lpanel @chose="chose"></lpanel>
		<lists v-if="selecty==3"></lists>
		<tasks v-if="selecty==2"></tasks>
		<leads v-if="selecty==1"></leads>
>>>>>>> 13559718fa7921edf7294f67f9e83f19a290c024
	</div>
</template>

<script>
import lpanel from '~/components/lpanel.vue'
import tasks from '~/components/tasks.vue'
import lists from '~/components/lists.vue'
<<<<<<< HEAD
import Leads from '~/components/leads.vue'
=======
import leads from '~/components/leads.vue'
>>>>>>> 13559718fa7921edf7294f67f9e83f19a290c024

export default {
  components: {
    lpanel,
    tasks,
    lists,
<<<<<<< HEAD
    Leads
=======
    leads,
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
>>>>>>> 13559718fa7921edf7294f67f9e83f19a290c024
  }
}
</script>

<style>
	.main {
		background-color: #000;
		display: flex;
<<<<<<< HEAD
		height: 100vh;
		min-width: 100%;
		position: relative;

=======
		min-width: 100%;
		position: relative;
>>>>>>> 13559718fa7921edf7294f67f9e83f19a290c024
		min-height: 100vh;
		position: absolute;
<<<<<<< HEAD
		flex-direction: column;
	}



=======
		flex-direction: row;
	}
>>>>>>> 13559718fa7921edf7294f67f9e83f19a290c024
</style>