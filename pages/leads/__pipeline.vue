<template>
	<div class="main">
      <lpanel :chose="1"></lpanel>
    	<leads :id="id"></leads>
   </div>
</template>

<script>
import leads from '~/components/leads.vue';
import lpanel from '~/components/lpanel.vue';

import axios from 'axios';

export default {
    
    components: {leads, lpanel},
    data(){
      return {
        id: this.$route.params._pipeline
      }
    },
    methods: {
      
    },
    mounted(){     
      console.log(this.pipeline)
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