<template>
  <div>
    <h2>My todolist</h2>
    <!-- goi su kien addTodo -->
    <add-todo v-on:addTodo="addTodo" />

    <ul>
      <li :key="todo.id" v-for="todo in todos">
        <todo :todo="todo" v-on:delete="deleteTodo" />
      </li>
    </ul>
  </div>
</template>

<script>
import todo from "./todo";
import addTodo from "./addTodo";

export default {
  name: "todos",
  components: {
    todo,
    addTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "lap trinh vue js",
          completed: false
        },
        {
          id: 2,
          title: "Lap trinh laravel",
          completed: false
        },
        {
          id: 3,
          title: "lap trinh ASP.NET",
          completed: false
        },
        {
          id: 4,
          title: "Lap trinh Java",
          completed: false
        },
        {
          i: 5,
          title: "Lap trinh C#",
          completed: false
        }
      ]
    };
  },
  methods: {
    addTodo(todoObject) {
      this.todos = [...this.todos, todoObject];
    },
    deleteTodo(todoId) {
      //   this.todos = this.todos.filter(todo => todo.id !== todoId);

      this.todos = this.todos.filter(function(todo) {
        return todo.id !== todoId;
      });

      /**
      [1, 2, 3, 4].filter(number => number !== 4)
      ===> [1, 2, 3]
       */
    }
  }
};
</script>

<style>
</style>