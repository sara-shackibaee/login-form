
<template>

  <div id="app1">
    <h1>{{titel}}</h1>
    <table class="table">
      <thead>
        <tr >
          <td>name</td>
          <td>family</td>
          <td>code</td>
          
        </tr>
      </thead>
      <tbody>
        <tr v-for="row in rows">
           <td><input type="text" v-model="row.name"></td>
           <td><input type="text" v-model="row.family"></td>
            <td><input type="text" v-model="row.code"></td>
          <td><a @click="removeRow(row)">Remove</a></td>

          
        </tr>
      </tbody>
    </table>
     <button  @click="addrow">Add</button>
  </div>
</template>

<script>
export default {
  name: 'Userinfo',
  data () {

    return {
        titel:"UserInfo",
        colomns:['firstname','lastname','code'],
        rows:[{name:"sara",family:"rezaee",code:123}]
       

        
    }
      
  },
  methods: {

    removeRow:function(row){
      console.log(row)
      this.rows.pop(row)
    },
    addrow:function(){
      this.rows.push({name:"",family:"",code:""})
    }
    
  }
  
}
</script>

