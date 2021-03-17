

<template>
  <div id="app">
      <div id="subapp" v-show="showform">
        <h1>{{titel}}</h1>
        <label>USER:</label>
        <input ref="input1"></input>
        <label>PASS:</label>
        <input ref="input2"></input>
        <button id="bt1"v-on:click="login">Login</button>
      </div>

      <div v-if="autenticated">
            <Userinfo/>
      </div>
        
  </div>
</template>


<script>
import  Userinfo  from './Userinfo.vue'
export default {
  name: 'app',
  data () {

    return {
        titel:"Login Form",
        name:null,
        pass:null,
        showform:true,
        autenticated:false,
        personinfo: {
            username: "admin",
            password: 123
		}
  
        
    }
    
      
  },

  components: {
    'Userinfo': Userinfo,
   
  },
  methods:{
        

        login:function(){

          this.name = this.$refs.input1.value,
          this.pass =  this.$refs.input2.value
              
          if(this.name==this.personinfo.username & this.pass==this.personinfo.password){

              this.autenticated = true
              this.showform = false
            }else{
              this.autenticated = false
              
            }
          
          
        },
        
                        
        },

  
}
</script>


<style scoped>


#app{
  max-width:800px;
  margin:2rem auto;
  border: 5px solid #382008;
  background-color:#34b7eb;
  padding:2rem;
  
}
button{
    background-color: #141413;
    padding:.5rem;
    color:white;
    margin:1rem 0;
    width:auto;
    text-transform:uppercase;
    cursor:pointer;
    
    font-size:18;
  }
  
  
  

input{
      display:block;
      width:100%;
      background-color: #f9fcf7;

  }
  

</style>