<template>
  <div>
    <ul>
      <li v-for="item in _chatItems" :key="item.key">{{item.val}}</li>
    </ul>
  </div>
</template>

<script>


export default {
  name: 'ChatList',
  components: {

  },
  props: {
    _chatItems: [],
  },
}
</script>

<style>

</style>
