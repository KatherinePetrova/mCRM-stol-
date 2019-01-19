<template>
	<div class="main">
      	<lpanel :chose="3"></lpanel>
    	<lists></lists>
   </div>
</template>

<script>
import lists from '~/components/lists.vue';
import lpanel from '~/components/lpanel.vue';

export default {
    
    components: {lists, lpanel},

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

.main {
  background-color: #000;
  display: flex;
  width: 100vw;
  position: relative;
  min-height: 100vh;
  position: absolute;
  flex-direction: row;
}
</style>