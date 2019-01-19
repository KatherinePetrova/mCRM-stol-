<template>
	<div class="lpanel">
		<div class="kvo"></div>
		<nuxt-link class="kvo" to="/leads">
			<iconDesktop :clicked="chose"></iconDesktop>
		</nuxt-link>
		<nuxt-link class="kvo" to="/leads">
			<iconLeads :clicked="chose"></iconLeads>
		</nuxt-link>
		<nuxt-link class="kvo" to="/tasks">
			<iconTasks :clicked="chose"></iconTasks>
		</nuxt-link>
		<nuxt-link class="kvo" to="/lists">
			<iconList :clicked="chose"></iconList>
		</nuxt-link>
		<nuxt-link class="kvo" to="/leads">
			<iconMail :clicked="chose"></iconMail>
		</nuxt-link>
		<nuxt-link class="kvo" to="/leads">
			<iconAnalytics :clicked="chose"></iconAnalytics>
		</nuxt-link>
		<nuxt-link class="kvo" to="/leads">
			<iconSettings :clicked="chose"></iconSettings>
		</nuxt-link>
		<div class="kvo last">			
			<iconChat></iconChat>
		</div>
	</div>
</template>

<script>
import iconChat from '~/components/icons/chat.vue';
import iconSettings from '~/components/icons/settings.vue';
import iconAnalytics from '~/components/icons/analytics.vue';
import iconMail from '~/components/icons/mail.vue';
import iconList from '~/components/icons/list.vue';
import iconTasks from '~/components/icons/tasks.vue';
import iconLeads from '~/components/icons/leads.vue';
import iconDesktop from '~/components/icons/desktop.vue';

export default {
	props: ['chose'],
	methods: {
		iconChose(ind){
			for(var i=0; i<this.chose.length; i++){
				this.chose[i] = false;
			}
			this.chose[ind] = true;
		}
	},
	components: {
		iconChat, iconSettings, iconAnalytics, iconMail, iconList, iconTasks, iconLeads, iconDesktop
  	}
  }
</script>

<style scoped>

	img {
		height: 50%;
	}

	.lpanel {
		min-height: 100vh;
		min-width: 70px;
		width: 70px;
		background-color: #1b3446;
		display: flex;
		flex-direction: column;
		position: fixed;
		top: 0;
		left: 0;
	}

	.kvo {
		min-width: 70px;
		width: 100%;
		min-height: 60px;
		height: 5vw;

		cursor: pointer;

		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;

		text-align: center;
		font-size: 0.65em;
		color: #AFAFAF;
		text-decoration: none;

		position: relative;
	}

	.kvo:hover {
		color: white;
	}

	.last {
		position: absolute;
		bottom: 0;

		background-color: #162b3a;

		border-top-style: solid;
		border-width: 1px;
		border-color: #224357;
	}

	.clicked {
		color: white;
	}
</style>