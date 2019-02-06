<template>
	<div class="main">
		<signin></signin>
	</div>
</template>

<script>
import signin from '~/components/sign_in.vue';

export default {
	transition: 'reg',
  components: {
    signin
  }
}
</script>

<style scoped>
	.main {
		display: flex;
		min-height: 100vh;
		min-width: 100vw;
		justify-content: center;
		align-items: center;
		position: absolute;
		flex-direction: column;
	}
</style>