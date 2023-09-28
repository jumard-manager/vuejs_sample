<template>
  <div>
    <textarea :style="`width:98%;`" v-model="chat"  @keydown="enter"></textarea>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
  name: 'ChatInput',
  components: {

  },
  data() {
    return {
      chat: '',
    }
  },
  methods: {
    enter: function(e) {
      if(e.keyCode === 13 && e.shiftKey === false) {
        e.preventDefault();
        this.$emit('_callback', {key:uuidv4(), val:e.target.value});
        this.chat = '';
      }
    }
  },
}
</script>

<style>

</style>
