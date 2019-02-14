<template>
<div>
<form v-on:submit.prevent="addTodo">
<input type="text" name="title" v-model="title" placeholder="Add Todo..." />
<input type="submit" value="Submit" class="btn" />
</form>
</div>
</div>
</template>

<script>

export default {
name: 'AddTodo',
data(){
return {
 title: ''
}
},
methods:{
addTodo(){
//create an object with the attributes 
  const newTodo = {
   id:"2344",
   title:this.title,
   completed:false
    
  }
//emit the event with the object as a parameter
 this.$emit('add-todo',newTodo);
//clear the input text box
this.title ="";
}
}

}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
form{
display: flex;
}
input[type="text"]{
flex: 10;
padding: 5px;
}
input[type="text"]{
flex: 2;
}
</style>
