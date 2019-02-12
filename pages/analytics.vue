<template>
	<div class="mainy">
      <lpanel :chose="5"></lpanel>
      <dev></dev>
   </div>
</template>

<script>
import lpanel from '~/components/lpanel.vue';
import signIn from '~/components/sign_in.vue';
import signUp from '~/components/sign_up.vue';
import dev from '~/components/developing.vue';

export default {
    
    components: {
      lpanel,
      // signIn,
      // signUp,
      dev
    },

    mounted(){     
      console.log('pop')
    },
}
</script>

<style scoped>
html, body {
    margin: 0;
    padding: 0;
}

.mainy {
  background-color: #000;
  display: flex;
  width: 100vw;
  min-height: 100vh;
  position: absolute;
  flex-direction: row;
}
</style>