<template>
  <div class="about">
    <input type="text" v-model="todo.title">
    <br>
    <input type="text" v-model="todo.body">
    <br>
    <button @click="saveTodo">Save</button>
    <p>{{message}}</p>
  </div>
</template>

<script lang="ts">
  import { defineComponent } from 'vue';
  import axios from 'axios';
  export default defineComponent({
    name: 'Home',
    data(){
      return {
        todo : {
          title : '',
          body : '',
          userId : 1
        },
        message : ''
      }
    },
    methods: {
      saveTodo(){
        axios.post('https://jsonplaceholder.typicode.com/posts')
        .then(res => {
          this.message = 'Todo created with id: ' + res.data.id
          this.todo.title = ''
          this.todo.body = ''
        })
      }
    }
  });
</script>

<style scoped>
  input{
    border: 1px solid #D2653E;
    border-radius: 5px;
    margin: 15px;
    padding: 10px;
    outline: none;
  }

  button{
    border: 1px solid #D2653E;
    background-color: #D2653E;
    color: white;
    border-radius: 5px;
    margin: 15px;
    padding: 10px;
  }
</style>