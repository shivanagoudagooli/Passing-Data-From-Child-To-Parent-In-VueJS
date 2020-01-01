<template>
    <div>
        USERNAME : {{username}}<br>
        <br>
        PASSWORD : {{password}}
    
        <br><br>
        <child/>
    </div>
</template>
<script>
import child from './child.vue';
import {Eventbus} from './eventbus.js'
export default {
    name:'parent',
    components:{
        child
    },
    data(){
        return {
            username:null,
            password:null,
            displayP : Boolean


        }
    },
 created() {
     /*eslint-disable*/
     console.log("created")
 Eventbus.$on('btn-click',this.calliFromChild)
 },
 mounted(){
     /*eslint-disable*/
     console.log("mounted")
     
 },

 
 methods:{
     calliFromChild(obj){

         console.log(obj.i + "from child");
         this.username=obj.i;
         this.password = obj.j;

     },
     displayBox(){
         if(username==="abc"||password===123){
             displayP = true;
         }else{
             displayP = false;
         }
        
     }
 }
    
}
</script>
<style scoped>

</style>