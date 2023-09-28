<template>
  <div class="main">
    <ComponentTemp title="Operator (plus / minus / multiplication / division)" />
    <hr/>
    <ComponentA v-if="isChk1" _operator="plus" @_callback="_getResult" />
    <ComponentA v-if="isChk2" _operator="minus" @_callback="_getResult" />
    <ComponentA v-if="isChk3" _operator="multiplication" @_callback="_getResult" />
    <hr/>
      Componet 1 ON/OFF : <input type='checkbox' v-model="isChk1" /><br/>
      Componet 2 ON/OFF : <input type='checkbox' v-model="isChk2" /><br/>
      Componet 3 ON/OFF : <input type='checkbox' v-model="isChk3" />
    <hr/>
  </div>
</template>

<script>
import ComponentTemp from './components/ComponentTemp.vue';
import ComponentA from './components/ComponentA.vue';

export default {
  name: 'App',
  components: {
    ComponentTemp,
    ComponentA,
  },
  data() {
    return {
        isChk1: true,
        isChk2: true,
        isChk3: true,
    }
  },
  methods: {
    _getResult : function (value) {
      console.log(value);
    }, 
  },
}
</script>

<style>
.main {
    text-align: left;
    margin: 30px;
}
</style>
