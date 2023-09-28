<template>
  <div class="main">
    <table border="1">
      <thead>
        <tr><th>Column 1</th><th>Column 2</th><th>Column 3</th><th>Delete</th></tr>
      </thead>
      <tbody>
        <tr v-for="data in datas" :key="data.key">
          <td>{{data.col1}}</td>
          <td>{{data.col2}}</td>
          <td>{{data.col3}}</td>
          <td><button @click="(e)=>del(e)">DEL</button></td>
        </tr>
      </tbody>

    </table>
    <hr/>
    <input type='text' v-model="col1" />&nbsp;/&nbsp;
    <input type='text' v-model="col2" />&nbsp;/&nbsp;
    <input type='text' v-model="col3" />&nbsp;
    <button @click="add" >ADD</button>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
  name: 'App',
  components: {
    
  },
  data(){
    return {
      datas: [{key:'k1',col1:'AAA',col2:'BBB',col3:'CCC'}],
      col1: '',
      col2: '',
      col3: '',
    }
  },
  methods: {
    add: function () {
      this.datas.push({key:uuidv4(),col1:this.col1,col2:this.col2,col3:this.col3});
    },
    del: function(e) {
      e.target.parentElement.parentElement.remove();
    },
  }
}
</script>

<style>
.main {
    text-align: left;
    margin: 30px;
}
</style>
