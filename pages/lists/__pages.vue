<template>
	<div class="main">
      <lpanel :chose="3"></lpanel>
    	<lists :page="$route.params._pages"></lists>
   </div>
</template>

<script>
import lists from '~/components/lists.vue';
import lpanel from '~/components/lpanel.vue';

export default {
    
    components: {lists, lpanel},
    data(){
      return {
      }
    },
    mounted(){  
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
  width: 100%;
  position: relative;
  min-height: 100vh;
  position: absolute;
  flex-direction: row;
}
</style>