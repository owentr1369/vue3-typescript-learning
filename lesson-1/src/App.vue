<template>
  <div class="app">
    <h1>Hello, {{ name }}'s here! I'm {{ age }} years old.</h1>
    <button v-on:click="changeName('Jack')">Change Name</button>
    <button v-on:click="changeAge(30)">Change Age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from "vue";

export default defineComponent({
  name: "App",
  setup() {
    // Reactive
    // const state = reactive({
    //   name: "Owen" as string,
    //   age: 25 as string | number,
    // });
    // return { ...toRefs(state) };

    // Ref
    const name = ref<string>("Owen");
    const age = ref<number | string>(25);
    return { name, age };
  },
  methods: {
    changeName(name: string) {
      this.name = name;
      return name;
    },
    changeAge(age: string | number) {
      this.age = age;
      return age;
    },
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
