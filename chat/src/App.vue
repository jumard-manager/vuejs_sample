<template>
  <div class="main">
    <table border="1" width="400px">
      <tbody>
        <tr>
          <td><ChatList :_chatItems="chatItems" /></td>
        </tr>
        <tr>
          <td><ChatInput @_callback="updateList" /></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>

import ChatList from './components/ChatList.vue';
import ChatInput from './components/ChatInput.vue';

export default {
  name: 'App',
  components: {
    ChatList,
    ChatInput,
  },
  data() {
    return {
      chatItems: [{key:'key1', val:'Hello!'}],
    }
  },
  methods: {
    updateList: function (_val) {
      this.chatItems.push(_val);
    }
  },
}
</script>

<style>
.main {
    text-align: left;
    margin: 30px;
}
</style>
