<template>
  <PostList />
</template>

<script>
  import PostList from './components/PostList.vue';

  export default {
    name: 'App',
    components: {
      PostList,
    },
  }
</script>

<style scoped>
  #app{
    text-align: center;
  }
</style>