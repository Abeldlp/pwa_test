<template>
  <div class="home">
    <img alt="Foodticket logo" src="../assets/logo.png">
    <todo-component v-for="todo in todos" :todo="todo" :key="todo.id"></todo-component>
  </div>
</template>

<script lang="ts">
  import { defineComponent } from 'vue';
  import axios from 'axios';
  import TodoComponent from '../components/TodoComponent.vue'
  export default defineComponent({
    name: 'Home',
    components: {
      TodoComponent
    },
    data(){
      return {
        todos : []
      }
    },
    mounted(){
      axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(res => this.todos = res.data)
    }
  });
</script>
