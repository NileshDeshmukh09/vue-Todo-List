<template>
   <div
      class="todo-item"
      v-bind:class="{ 'is-complete' : todo.completed }">
      <p>
         <input
            type="checkbox"
            v-on:change="markComplete">
            {{ todo.title }}

         <button @click="$emit('del-todo', todo.id)" class="del"> x </button>
      </p>
   </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
    /* eslint-disable */ 
      this.todo.completed = !this.todo.completed; // eslint-disable-next-lin
      // console.log(123);
    },
  },
};
</script>

<style scoped>
.todo-item {
  background: rgb(220, 163, 163);
  padding: 10px;
  border-bottom: 1px dotted rgb(165, 102, 102);
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: red;
  color: antiquewhite;
  border: none;
  border-radius: 50%;
  width: 20px;
  height: 20px;
  cursor: pointer;
  float: right;
}
</style>