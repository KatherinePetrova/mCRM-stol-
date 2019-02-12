<template>
	<div class="main">
      <lpanel :chose="1"></lpanel>
    	<lead :lead="lead" :tags="tags" :vklads="vklads" :select_task="select_task" :ready="ready" :selected_vklad="0"></lead>
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
            data: {where: {group_id: vklads[i].id, lcc_id: 1}},
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

        if(lead.main_contact_id){
          var main_contact = await axios('http://crm.aziaimport.kz:3000/api/where/contacts/0', {
            method: 'post',
            data: {where: {id: lead.main_contact_id}},
            withCredentials: true
          });

          lead.main_contact = main_contact.data[0];
          
        } else {
          lead.main_contact = {}
        }

        lead.main_contact.clicked = true;

        var add_contacts = await axios('http://crm.aziaimport.kz:3000/api/where/leads_contacts/0', {
          method: 'post',
          data: {where: {leads_id: lead.main_contact_id}},
          withCredentials: true
        });

        add_contacts = add_contacts.data;
        lead.add_contacts = [];
        
        for(var i=0; i<add_contacts.length; i++){
          if(add_contacts[i].contact_id!=lead.main_contact.id){
            var add_single = await axios('http://crm.aziaimport.kz:3000/api/where/contacts/0', {
              method: 'post',
              data: {where: {id: add_contacts[i].contact_id}},
              withCredentials: true
            });
            add_single.data[0].clicked = false;
            lead.add_contacts.push(add_single.data[0]);            
          }
        }

        var cStroks = await axios('http://crm.aziaimport.kz:3000/api/where/custom_fields/0', {
          method: 'post',
          data: {where: {lcc_id: 2}},
          withCredentials: true
        });
        
        lead.main_contact.stroks = cStroks.data;
        for(var i=0; i<lead.add_contacts.length; i++){
          lead.add_contacts[i].stroks = cStroks;
        }

        for(var i=0; i<lead.main_contact.stroks.length; i++){
          var mainCStroks = await axios('http://crm.aziaimport.kz:3000/api/where/contacts_value/0', {
            method: 'post',
            data: {where: {field_id: lead.main_contact.stroks[i].id, contact_id: lead.main_contact.id}},
            withCredentials: true
          });

          if(mainCStroks.data.length!=0){
            lead.main_contact.stroks[i].value = mainCStroks.data[0].value
          } else {
            lead.main_contact.stroks[i].value = "";
          }
        }

        for(var i=0; i<lead.add_contacts.length; i++){
          for(var j=0; j<lead.add_contacts[i].stroks.length; j++){
            var mainCStroks = await axios('http://crm.aziaimport.kz:3000/api/where/contacts_value/0', {
              method: 'post',
              data: {where: {field_id: lead.add_contacts[i].stroks[j].id, contact_id: lead.add_contacts[i].id}},
              withCredentials: true
            });

            if(mainCStroks.data.length!=0){
              lead.add_contacts[i].stroks[j].value = mainCStroks.data[0].value;
            } else {
              lead.add_contacts[i].stroks[j].value = "";
            }
          }
        }
                
        console.log(lead);
        var ready = true;
        return {
          ready, lead, tags, vklads,
          select_task: ''
        }
      } catch(e){
        console.log(e)
        var ready = false;
        return {
          ready
        }
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