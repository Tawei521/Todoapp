<template>
  <div id="app">
    <router-view></router-view>
    <todo-app></todo-app>
    
  </div>
</template>

<script>
import TodoApp from './components/TodoApp.vue'

export default {
  name: 'App',
  components: {
    TodoApp
  }
}
</script>



