<template>
	<div class="main_sign">
		<div class="window_sign">
			<span style="margin-bottom: 50px;">Вход</span>
			<form @submit.prevent class="form_sign">
				<input class="input" type="text" placeholder="Имя пользователя" required>
				<input class="input" type="password" placeholder="Пароль" required>
				<div class="aa" style="display: flex; justify-content: center;">
					<a href="#">Регистрация</a>
				</div>
				<input class="input" type="submit" value="Войти" style="width: 50% ">
				<nuxt-link to="/leads" style="font-size: 1rem">Обходная ссылка</nuxt-link>
			</form>
		</div>
	</div>
</template>

<script>

export default {
  components: {

  },
  data(){
	  return {

	  }
  }
}
</script>

<style scoped>
	.main_sign {
		height: 100vh;
		width: 100%;
		background-color: #f5f5f5;
		display: flex;
		justify-content: center;
		align-items: center;

	}

	.window_sign {
		width: 30%;
		height: 70%;
		background-color: #fff;
		border: 1px solid #d3d6d7;
		box-shadow: 0 14px 24px 1px rgba(0,0,0,.1);
			webkit-transition: opacity .1s,-webkit-transform .3s;
    		transition: transform .3s,opacity .1s;
    		transition: transform .3s,opacity .1s,-webkit-transform .3s;
    	border-radius: 1px;
    	display: flex;
    	flex-direction: column;
    	align-items: center;
    	padding: 30px;
		font-size: 2em;
		font-weight: bold;
	}

	.form_sign {
		height: 50%;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		width: 100%;
		align-items: center;
	}

	.input {
		width: 100%;
		font-size: 1.3rem;
		
	} 

	.aa {
		font-size: 1rem;
	}
</style>