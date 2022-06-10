<template>
  <h2>Child子级组件</h2>
  <h3>msg: {{ msg }}</h3>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "Child",
  props: ["msg"],

  // setup细节问题:
  // setup是在beforeCreate生命周期回调之前就执行了,而且就执行一次
  // 由此可以推断出:setup在执行的时候,当前的组件还没有创建出来,也就意味着:组件实例对象this根本就不能用
  // this是undefined,说明,就不能通过this再去调用data/computed/methods/props中的相关内容了
  // 其实所有的composition API相关回调函数中也都不可以

  // setup中的返回值是一个对象,内部的属性和方法是给html模板使用的

  // 数据初始化的生命周期回调
  beforeCreate() {
    console.log("beforeCreate执行了");
  },
  // 界面渲染完毕
  //mounted() {},
  setup() {
    console.log("setup执行了", this);

    return {
      //   setup中一般都是一个对象,对象中的属性和方法都可以在html模板中直接使用
    };
  },
});
</script>