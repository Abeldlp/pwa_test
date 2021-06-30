<template>
  <div class="detail">
    <h1>This is an detail for {{$route.params.id}}</h1>
    <h2>Title fetched from api: {{ todo.title }}</h2>
    <p>Body fetched from api below</p>
    <h3>{{ todo.body }}</h3>
  </div>
</template>

<script lang="ts">
  import { defineComponent } from 'vue';
  import axios from 'axios';

  export default defineComponent({
    name: 'Detail',

    data(){
      return {
        todo : {}
      }
    },
    mounted(){
      axios.get('https://jsonplaceholder.typicode.com/posts/' + this.$route.params.id)
        .then(res => this.todo = res.data)
    }
  });
</script>


