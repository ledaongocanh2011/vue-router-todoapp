<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>


<template>
  <div>
    <template v-if="isUpdate">
      <input type="text" v-model="todo.title" />
    </template>
    <p v-else>{{todo.title}}</p>
    <button v-on:click="$emit('delete',todo.id)">delete</button>
    <button v-if="isUpdate" @click="isUpdate = false">save</button>
    <button v-else @click="isUpdate = true">edit</button>
    <!-- trong if phải có giá trị là bool sao e lại viết phép gán vào ...
    bieu thuc dieu kien a -->
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
  methods: {
    
  }
};
</script>

<style>
</style>
