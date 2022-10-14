<template>
  <div id="app">
    <ToDoList></ToDoList>
  </div>
</template>

<script>
import ToDoList from './components/ToDolist/index.vue'
export default {
  name: 'App',
  components:{
    ToDoList
  }  
}
</script>

<style> /* scoped 私有*/
body,html{
  background-color: #CDCDCD;
}
</style>