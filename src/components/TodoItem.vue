<template>
  <div class="todo-item" v-bind:class="{'is-completed': todo.completed}">
    <p>
    <input type="checkbox" v-on:change="toggleCompleted" />
    {{ todo.title }}
    <button v-on:click="$emit('del-todo',todo.id)" class="del">
      <span class="fa fa-trash-alt"></span>
    </button>
    </p>

  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: [
  "todo"
  ],
  methods:{
  toggleCompleted(){
   this.todo.completed = !this.todo.completed; 
  }
      
  }
  
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.todo-item{
background: #f4f4f4;
padding: 10px;
border-bottom: 1px #ccc dotted
}

.is-completed{
text-decoration: line-through;
}

.del{
background: #ff0000;
color: #fff;
border: none;
padding: 1px 5px;
border-radius: 50%;
cursor: pointer;
float: right;


}

</style>
