<template>
    <v-container class="pa-0 my-0">
        <v-layout wrap align-center justify-center row fill-height class="mt-2 elevation-2 white" style="border:1px solid #e0e0e0;border-radius:5px">
           <v-flex xs12 sm8 md9 lg9 class="pa-2 py-4 px-3" > 
               <p class="google-font mt-2 mb-1" style="font-size:115%;color:#757575">
                   {{eventDetails.EventDescription}}
               </p>
               <p class="google-font mt-2 mb-1" style="font-size:115%;color:#757575">
                   {{eventDetails.LeadDescription}}
               </p>
                
                <v-btn color="#1a73e8" v-if="eventDetails.RegistrationLink.length>0" href="https://forms.gle/qbwrDJBxKQNSuCWV6" target="_blank" dark style="text-transform: capitalize;border-radius:5px;"> 
                    Become a Speaker
                </v-btn>
                &nbsp;
                &nbsp;
                 <v-btn color="#1a73e8" v-if="eventDetails.RegistrationLink.length>0" href="https://docs.google.com/forms/d/e/1FAIpQLSebHQB2PwsgFytP2LyGqiNMQ7mgJLUXM2vLiJi7awFJNrJ8Vg/viewform" target="_blank" class="ma-0 elevation-0 my-2" dark style="text-transform: capitalize;border-radius:5px;"> 
                    Become a Lead
                </v-btn>
                
            
            </v-flex> 
        </v-layout>

    </v-container>
</template>

<script>
import eventDetails from '@/assets/data/featureEvent.json'
export default {
    components:{
    },
    data() {
        return {
            eventDetails:eventDetails
        }
    },
    created(){
        
    },
    methods:{
        getImgUrl(pic) {
            if(pic.length>0){
                return require('@/assets/img/featureEvent/'+pic)
            }else{
                return require('@/assets/img/featureEvent/imagenotfound.png')
            }
        },
    },
    filters:{
        summery: (val,num)=>{
            return val.substring(0,num)+".."
        },
        dateFilter: (value)=>{
            const date = new Date(value)
            return date.toLocaleString(['en-US'], {month: 'short', day: '2-digit', year: 'numeric'})
        }
    }
}
</script>
