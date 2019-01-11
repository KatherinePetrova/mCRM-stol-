<template>
	<div class="main">
		<leads></leads>
		<!-- <nuxt-link to="/" style="margin-top: 20px">Перейти</nuxt-link> -->
	</div>
</template>

<script>
import Leads from '~/components/leads.vue'

export default {
  components: {
    Leads,
  }
}
</script>

<style>
	.main {
		background-color: #000;
		display: flex;
		min-height: 100vh;
		min-width: 100vw;
		/*justify-content: center;*/
		align-items: center;
		position: absolute;
		flex-direction: column;
	}
</style>