<template>
  <div id="app">
  <HeaderPage />
    <TodosPage v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import HeaderPage from './components/layouts/HeaderPage.vue';
import TodosPage from './components/TodosPage.vue';

export default {
  name: 'App',
  components: {
    HeaderPage,
    TodosPage,
  },
   data(){
    return {
      todos : [
        {
          id : 1,
          title : "Todo One",
          completed : false
        },
        {
          id : 2,
          title : "Todo Two",
          completed : true
        },
        {
          id : 3,
          title : "Todo Three",
          completed : false
        },
      ]
    }
   },
   methods : {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
      console.log("data has clicked !");
    }
   }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
