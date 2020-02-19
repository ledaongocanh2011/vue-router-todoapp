<template>
  <div>
    <template v-if="isUpdate == true">
      <input type="text" v-model="todo.title" />
    </template>
    <p v-else>{{todo.title}}</p>
    <button v-on:click="$emit('delete',todo.id)">delete</button>
    <button v-if="isUpdate" @click="isUpdate = false">save</button>
    <button v-else @click="isUpdate = true">edit</button>
    <!-- trong if phải có giá trị là bool sao e lại viết phép gán vào ...
    bieu thuc dieu kien a-->
  </div>
</template>

<script>
export default {
  name: "todo",
  props: ["todo"],
  data() {
    return {
      isUpdate: false
    };
  },
  methods: {}
};
</script>

<style>
</style>