<template>
	<div class="main">
      <lpanel :chose="1"></lpanel>
    	<lead></lead>
   </div>
</template>

<script>
import lead from '~/components/single_lead.vue';
import lpanel from '~/components/lpanel.vue';

export default {
    
    components: {lead, lpanel},

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