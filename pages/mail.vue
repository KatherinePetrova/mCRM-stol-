<template>
	<div class="mainy">
      	<lpanel :chose="4"></lpanel>
    	<mail></mail>
   </div>
</template>

<script>
import mail from '~/components/mail.vue';
import lpanel from '~/components/lpanel.vue';

export default {
    
    components: {
      lpanel,
      mail
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
  position: relative;
  min-height: 100vh;
  position: absolute;
  flex-direction: row;
}
</style>