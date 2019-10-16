<template>
  <div>
      
      <div v-for ="todo in todos" :key="todo.id">
       
       
       <h3><todoItem :todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" /></h3> 
       


      </div>
  </div>
</template>

<script>
 import todoItem from './todoItem.vue';
export default {
    name: 'todo',
    props: ["todos"],
    components: {
      todoItem
    },
   
    
   
 

  
}
</script>

