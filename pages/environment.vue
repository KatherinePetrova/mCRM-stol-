<template>
	<div class="main">
		<lpanel></lpanel>
		<!-- <tasks></tasks> -->
		<lists></lists>
	</div>
</template>

<script>
import lpanel from '~/components/lpanel.vue'
import tasks from '~/components/tasks.vue'
import lists from '~/components/lists.vue'

export default {
  components: {
    lpanel,
    tasks,
    lists
  }
}
</script>

<style scoped>
	.main {
		display: flex;
		height: 100vh;
		min-width: 100%;
		position: relative;
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