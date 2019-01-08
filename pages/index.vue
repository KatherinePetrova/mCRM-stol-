<template>
	<div class="main">
		<logo></logo>
		<nuxt-link to="/environment" style="margin-top: 20px">Перейти</nuxt-link>
	</div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
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
