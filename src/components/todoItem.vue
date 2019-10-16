<template>

   <div class="todo-item" v-bind:class="{'is-completed':todo.status}">
      <p><input type="checkbox" name="" id="" @click="todo.status= !todo.status">
       {{todo.title}}  <button class="del" @click="$emit('del-todo', todo.id)" >delete</button></p>
   </div> 
</template>


<script>
export default {
    name: "todoItem",
    props:["todo"]

}
</script>



<style  scoped>
.todo-item{
  background: #f4f4f4;
  /* padding: 10px; */
  padding:30px; 
  border-bottom: 1px #ccc dotted;
  width: 100%;
  /* margin: auto */
}

.is-completed {
  text-decoration: line-through;
}


.del{
 background:rgb(204, 56, 56);
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 10%;
  cursor: pointer;
  float: right;
}


</style>

