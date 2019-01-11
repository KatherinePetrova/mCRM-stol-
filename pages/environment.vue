<template>
	<div class="main">
		<lpanel></lpanel>
		<!-- <tasks></tasks> -->
		<lists></lists>
		<leads></leads>
	</div>
</template>

<script>
import lpanel from '~/components/lpanel.vue'
import tasks from '~/components/tasks.vue'
import lists from '~/components/lists.vue'
import Leads from '~/components/leads.vue'

export default {
  components: {
    lpanel,
    tasks,
    lists,
    Leads
  }
}
</script>

<style>
	.main {
		background-color: #000;
		display: flex;
		height: 100vh;
		min-width: 100%;
		position: relative;

		min-height: 100vh;
		min-width: 100vw;
		/*justify-content: center;*/
		align-items: center;
		position: absolute;
		flex-direction: column;
	}



</style>