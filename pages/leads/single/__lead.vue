<template>
	<div class="main">
      <lpanel :chose="1"></lpanel>
    	<lead :lead="lead" :tags="tags" :vklads="vklads" :select_task="select_task" :ready="ready" :nony="nony"></lead>
   </div>
</template>

<script>
import lead from '~/components/single_lead.vue';
import lpanel from '~/components/lpanel.vue';
import axios from 'axios';

export default {
    transition: 'bounce',
    components: {lead, lpanel},
    async asyncData({params}){
      try {
        var lead = await axios('http://crm.aziaimport.kz:3000/api/where/leads/0', {
          method: 'post',
          data: {where: {id: params._lead}, orderby: 'created_at'},
          withCredentials: true
        });

        lead = lead.data[0];

        var created_by = await axios('http://crm.aziaimport.kz:3000/api/where/users/0', {
          method: 'post',
          data: {where: {id: lead.created_by}},
          withCredentials: true
        });

        created_by = created_by.data[0]
        lead.created_by = created_by;

        var tags = await axios('http://crm.aziaimport.kz:3000/api/where/tags_link/0', {
          method: 'post',
          data: {where: {related_id: params._lead, type: 'leads'}, orderby: 'created_at'},
          withCredentials: true
        });
        tags = tags.data;

        for(var i=0; i<tags.length; i++){
          var stag = await axios('http://crm.aziaimport.kz:3000/api/where/tags/0', {
            method: 'post',
            data: {where: {id: tags[i].tags_id}},
            withCredentials: true
          });

          tags[i] = stag.data[0];
        }

        var vklads = await axios('http://crm.aziaimport.kz:3000/leads/select/card_groups', {
          method: 'post',
          withCredentials: true
        });
        vklads = vklads.data;

        for(var i=0; i<vklads.length; i++){
          var strok = await axios('http://crm.aziaimport.kz:3000/api/where/custom_fields/0', {
            method: 'post',
            data: {where: {group_id: vklads[i].id}},
            withCredentials: true
          });
          vklads[i].stroks = strok.data;
          
          for(var j=0; j<vklads[i].stroks.length; j++){
            
            var val = await axios('http://crm.aziaimport.kz:3000/api/where/leads_value/0', {
              method: 'post',
              data: {where: {leads_id: lead.id, field_id: vklads[i].stroks[j].id}},
              withCredentials: true
            });

            if(val.data.length!=0){
              vklads[i].stroks[j].value = val.data[0].value;
            } else {
              vklads[i].stroks[j].value = ''
            }
          }
        }

        var step = await axios('http://crm.aziaimport.kz:3000/api/where/step/0', {
          method: 'post',
          data: {where: {id: lead.status}},
          withCredentials: true
        });

        lead.step = step.data[0];

        var pipeline = await axios('http://crm.aziaimport.kz:3000/api/where/pipelines/0', {
          method: 'post',
          data: {where: {id: lead.step.pipeline_id}},
          withCredentials: true
        });

        lead.pipeline = pipeline.data[0];

        console.log(lead);

        return {
          ready: true,
          lead, tags, vklads,
          nony: false,
          select_task: ''
        }
      } catch(e){
        console.log(e)
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
  width: 100vw;
  position: relative;
  min-height: 100vh;
  position: absolute;
  flex-direction: row;
}
</style>