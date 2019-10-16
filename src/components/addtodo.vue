<template>
  <div>
    <form @submit="addTodo">
      <input type="text" style="width: 70%;" v-model="title" name="title" placeholder="Add Todo.." />
      <input type="submit" value="submit" class="btn" />
    </form>
  </div>
</template>

<script>
// import uuid from 'uuid';
export default {
  name: "addtodo",
  data(){
      return{
          title: ''
      }
  },
   methods: {
       addTodo(e){
           e.preventDefault();
           const newtodo = {
            //    id: uuid.v4(),
               title: this.title,
               status:false
           }
           this.$emit('add-todo',newtodo);
           this.title="";
       }
   }
};
</script>

<style  scoped>
form {
  display: flex;
}
input[type="text"] {
    margin-top: 10px;
    border: 3px rgb(204, 56, 56) solid;
  flex: 10;
  padding: 5px;
}
input[type="submit"] {
    margin-top: 10px;
   background: #333;
   color: white;
  flex: 2;
}
</style>
