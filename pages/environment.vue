<template>
	<div class="main">
		<lpanel></lpanel>
	</div>
</template>

<script>
import lpanel from '~/components/lpanel.vue'

export default {
  components: {
	lpanel
  }
}
</script>

<style scoped>
	.main {
		display: flex;
		min-height: 100vh;
		min-width: 100vw;
		position: absolute;
		flex-direction: column;
	}
</style>