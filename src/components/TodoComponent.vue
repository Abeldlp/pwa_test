<template>
  <div class="todo">
      <router-link :to="'/details/' + todo.id">
          <p>{{todo.title}}</p>
      </router-link>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'TodoComponent',
  props: {
    todo: Object,
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    p{
        width: 80%;
        border-radius: 5px;
        padding: 10px;
        margin: 15px auto;
        -webkit-box-shadow: 0px 4px 15px -5px #d2653e73; 
        box-shadow: 0px 4px 15px -5px #d2653e5d;
    }
    
    a {
    color: #D2653E;
    text-decoration: none;
    }
</style>
