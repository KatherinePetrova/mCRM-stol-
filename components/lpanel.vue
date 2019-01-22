<template>
	<div class="lpanel">
		<div class="kvo" @click="cl"><img src="/mans.jpg" alt=""></div>
		<div class="kvo" @click="chose=0; $emit('chose', 0)">
			<iconDesktop :clicked="chose"></iconDesktop>
		</div>
		<div class="kvo" @click="chose=1; $emit('chose', 1)">
			<iconLeads :clicked="chose"></iconLeads>
		</div>
		<div class="kvo" @click="chose=2; $emit('chose', 2)">
			<iconTasks :clicked="chose"></iconTasks>
		</div>
		<div class="kvo" @click="chose=3; $emit('chose', 3)">
			<iconList :clicked="chose"></iconList>
		</div>
		<div class="kvo" @click="chose=4; $emit('chose', 4)">
			<iconMail :clicked="chose"></iconMail>
		</div>
		<div class="kvo" @click="chose=5; $emit('chose', 5)">
			<iconAnalytics :clicked="chose"></iconAnalytics>
		</div>
		<div class="kvo" @click="chose=6; $emit('chose', 6)">
			<iconSettings :clicked="chose"></iconSettings>
		</div>
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
	data(){
		return {
			chose: 0
		}
	},
	methods: {
		iconChose(ind){
			for(var i=0; i<this.chose.length; i++){
				this.chose[i] = false;
			}
			this.chose[ind] = true;
			console.log(this.chose)
		},
		cl(){
			console.log(this.chose)
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
		min-width: 65px;
		width: 5vw;
		background-color: #1b3446;
		display: flex;
		flex-direction: column;
	}

	.kvo {
		min-width: 65px;
		width: 5vw;
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

		position: relative;
	}

	.kvo:hover {
		color: white;
	}

	.kvo img {
		height: 65px;
		width: 65px;
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