<template>
	<div class="mainy">
      	<lpanel :chose="0"></lpanel>
    	  <desktop></desktop>
   </div>
</template>

<script>
import desktop from '~/components/desktop.vue';
import lpanel from '~/components/lpanel.vue';

export default {
    
    components: {desktop, lpanel},

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