<template>
  <div class="header">
     <h1>Todo List</h1> 
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header{
text-align: center;
background: #333;
color: #fff;
padding: 10px;
}

.header a{
color: #fff;
padding: right;
}
</style>
