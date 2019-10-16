<template>
  <div id="app">
   
     <addtodo v-on:add-todo="addTodo"/>
    <todo v-bind:todos="todos" v-on:del-todo="deleteTodo" />
   
  </div>
</template>

<script>
import todo from "../components/todo.vue";

import addtodo from "../components/addtodo.vue";
import axios from "axios";

export default {
  name: "home",

  components: {
    todo,
    addtodo
  },
  data() {
    return {
      todos: [
        // {
        //   id: 1,
        //   title: "Clean the house",
        //   status: false
        // },
        // {
        //   id: 2,
        //   title: "Read and Understand",
        //   status: false
        // },
        // {
        //   id: 3,
        //   title: "Watch the Flash S06",
        //   status: false
        // },
        // {
        //   id: 4,
        //   title: "Go to the Market",
        //   status: false
        // },
        // {
        //   id: 5,
        //   title: "Play football with Dami",
        //   status: false
        // }
      ]
    };
  },
  methods: {
    deleteTodo(id){
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then(res => this.todos=this.todos.filter(todo=>todo.id !== id))
      .catch(err => console.log(err));
      // this.todos=this.todos.filter(todo=>todo.id !== id);
    },
    addTodo(newtodo){
      const {title,completed}=newtodo;
      axios.post('https://jsonplaceholder.typicode.com/todos',{
        title,completed
      })
      .then(res => this.todos.push(newtodo))
      .catch(err => console.log(err));
      
    },
    
  },
  created(){
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(res => this.todos=res.data)
    .catch(err=> console.log(err));

  }
};
</script>

<style  scoped>
*{
  box-sizing:border-box;
  margin: 0;
  padding: 0;
}
body{
  font-family: arial,helvetica,sans-serif;
  line-height: 1.4;
}
.btn{
  cursor:pointer;
  padding:7px 20px;
  text-transform: capitalize;
  display: inline;
}
.btn:hover{
  background:#666
}
</style>

