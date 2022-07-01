<template>
  <div>哈哈，我又变帅了</div>
  <h1>{{ number }}</h1>
</template>

<script lang="ts">
// defineComponent函数,目的是定义一个组件,内部可以传入一个配置对象
import { defineComponent } from "vue";

export default defineComponent({
  // 当前组件的名字是App
  name: "App",
  setup() {
    const number = 10;
    return {
      number,
    };
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
