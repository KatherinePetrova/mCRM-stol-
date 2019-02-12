<template>
	<div class="main">
      <lpanel :chose="1"></lpanel>
    	<leads :groups="groups" :pipeline="pipeline" :id="id"></leads>
   </div>
</template>

<script>
import leads from '~/components/leads.vue';
import lpanel from '~/components/lpanel.vue';

import axios from 'axios';

export default {
    async asyncData({params}){
      try{
        let pipeline = await axios('http://crm.aziaimport.kz:3000/leads/select/pipelines', {
          method: 'post',
          withCredentials: true
        });

        pipeline = pipeline.data;

        let groups = [];

        let steps = await axios('http://crm.aziaimport.kz:3000/api/where/step/0', {
          method: 'post',
          withCredentials: true,
          data: {where: {pipeline_id: params._pipeline}}
        });
        groups = steps.data;

        for(var i=0; i<groups.length; i++){
          groups[i].count = 0;
          let leads = await axios(`http://crm.aziaimport.kz:3000/api/where/leads/0`, {
            method: 'post',
            withCredentials: true,
            data: {where: {status: groups[i].id}, orderby: 'created_at'}
          });

          leads = leads.data;

          for(var j=0; j<leads.length; j++){
            let leads_company = await axios(`http://crm.aziaimport.kz:3000/api/where/leads_company/0`, {
              method: 'post',
              withCredentials: true,
              data: {where: {id: leads[j].leads_company_id}}
            });

            leads_company = leads_company.data[0];

            leads[j].company = leads_company;

            var leads_contact = await axios(`http://crm.aziaimport.kz:3000/api/where/contacts/0`, {
              method: 'post',
              withCredentials: true,
              data: {where: {id: leads[j].main_contact_id}}
            });

            leads[j].contact = leads_contact.data[0];
          }
          

          groups[i].leads = leads;
          if(!groups[i].leads[0]) groups[i].leads = [];
        }

        console.log(groups)
        return {
          pipeline,
          groups,
          ready: true,
          id: params._pipeline
        }
      } catch(e){
          console.log(e)
      }
      
    },
    methods: {
      
    },
    components: {leads, lpanel},
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
  width: 100vw;
  position: relative;
  min-height: 100vh;
  position: absolute;
  flex-direction: row;
}
</style>