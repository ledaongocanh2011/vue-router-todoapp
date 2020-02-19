<template>
  <div id="app">
    <router-view />
    <router-link :to="{ name: 'HelloWorld' }">Home</router-link>
    <router-link to="/todos">List</router-link>

    <footer>
      <h1>Footer</h1>
    </footer>
  </div>
</template>

<script>
import todos from "./components/todos";

export default {
  name: "App",
  data() {
    return {};
  },
  components: {
    todos: todos
  },
  methods: {
    watch: {
      input: function() {
        if (
          isLocalStorage() /* function to detect if localstorage is supported*/
        ) {
          localStorage.setItem("storedData", this.input);
        }
      }
    }
  }
};

</script>

<style>
</style>
