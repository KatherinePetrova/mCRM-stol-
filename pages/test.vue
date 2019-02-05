<template>
    <div>{{pop}}</div>
</template>
<script>
import axios from 'axios';

export default {
    async asyncData(){
        
        try{
            var steps = await axios('http://crm.aziaimport.kz:3000/api/where/step/0', {
				method: 'post',
				withCredentials: true,
				data: {where: {pipeline_id: this.id}}
			});
			this.groups = steps.data;

			for(var i=0; i<this.groups.length; i++){
				this.groups[i].count = 1;
				var leads = await axios('http://crm.aziaimport.kz:3000/api/where/leads/0', {
					method: 'post',
					withCredentials: true,
					data: {where: {status: this.groups[i].id}, orderby: 'created_at'}
				});
				
				this.groups[i].leads = leads.data;
				if(!this.groups[i].leads[0]) this.groups[i].leads = [];
			}
            return {
                pop: query
            }
        }catch(e){
            console.log(e);
        }
    }
}
</script>
