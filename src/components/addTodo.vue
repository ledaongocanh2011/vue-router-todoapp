<template>
  <div class="addTodo">
    <form action>
      <input type="text" v-model="title" v-on:keyup.enter="addTodo" />
      <button type="submit" v-on:click.prevent="addTodo">add</button>
    </form>
  </div>
</template>

<script>
import uuid from "uuid";
export default {
  name: "addTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo() {
      if (this.title.length == 0) {
        return;
      }

      //   khoi tao mot obj chua data
      let todoObj = {
        id: uuid.v4(),
        title: this.title,
        completed: false
      };

      //   su dung emit de gui su kien add-todo ra ngoai component
      this.$emit("addTodo", todoObj);
      this.title = "";
    }
  }
};
</script>

<style>
</style>
