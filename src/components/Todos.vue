<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
    <h3><TodoItem v-on:del-todo="$emit('del-todo',todo.id)" v-bind:todo="todo" /></h3>
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  name: 'Todos',
  props: ["todos"],
  components:{
  TodoItem
  }

  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  /* margin: 40px 0 0; */
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
