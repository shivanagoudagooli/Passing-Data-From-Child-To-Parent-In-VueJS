<template>
  <div>
  
    Enter UserName : <input type="text" value="" id="user"/> <br>
    <br><br>
    Enter Password : <input type="password" value="" name="password"  id="psw"/><br>
    <br><br>
    <input type="button" v-on:click="getInputValue()" value="ok" />
        <br><br>
    <div>
        <div v-if="message">
            <p>{{message}}</p>
        </div>
        
    </div>
  </div>
</template>


<script>
import {Eventbus} from './eventbus.js'
export default {
  name: 'child',
  data() {
    return {
      username: '',
      password: '',
      message:null
    }
  },
  created(){

  },
  methods:{
    getInputValue(){
      let obj={}
      let i=document.getElementById("user").value;
      let j = document.getElementById("psw").value;
      obj.i= i;
      obj.j = j;
      if(i === "abc" || j=== 123 ){
        
        this.message = "The username and password are correct";
      }else{
          this.message = "The username and password are incorrect";
        
      }
      /*eslint-disable*/
       console.log("obj>>",obj)
     Eventbus.$emit("btn-click",obj)
    }
  }

}
</script>

<style scoped>

</style>
