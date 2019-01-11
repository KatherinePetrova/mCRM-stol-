<template>
	<div class="main">
<<<<<<< HEAD
		<lpanel></lpanel>
		<!-- <tasks></tasks> -->
		<lists></lists>
=======
		<leads></leads>
		<!-- <nuxt-link to="/" style="margin-top: 20px">Перейти</nuxt-link> -->
>>>>>>> bc9b1dbf6841866be2764343259d587a9aa7c2e6
	</div>
</template>

<script>
<<<<<<< HEAD
import lpanel from '~/components/lpanel.vue'
import tasks from '~/components/tasks.vue'
import lists from '~/components/lists.vue'

export default {
  components: {
    lpanel,
    tasks,
    lists
=======
import Leads from '~/components/leads.vue'

export default {
  components: {
    Leads,
>>>>>>> bc9b1dbf6841866be2764343259d587a9aa7c2e6
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
		min-height: 100vh;
		min-width: 100vw;
		/*justify-content: center;*/
		align-items: center;
		position: absolute;
		flex-direction: column;
>>>>>>> bc9b1dbf6841866be2764343259d587a9aa7c2e6
	}

/*	.content {
		background-color: #f5f5f5;
		padding: 15px;
		position: absolute;
		top: 65px;
		left: 65px;
		height: 100%;
		width: 100%;
	}*/

</style>