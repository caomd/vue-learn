<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg='<span style="color:#fff">Hello world</span>' />
    <ev />
    <com :age="age" @patch="handleChild">
      <h1 slot="a">我要加东西32</h1>
      <h1 slot="b">我在上边</h1>
    </com>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import "./components/n";
import ev from "./components/events.vue";
import com from "./components/com.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    ev,
    com,
  },
  data() {
    return {
      age: 10,
    };
  },
  beforeCreate() {
    console.log("beforeCreate");
  },
  beforeMount() {
    console.log("beforeMount");
  },
  created() {
    // 组件创建完后获取数据，
    // 此时 data 已经被 observed 了
    console.log("created");
  },
  methods: {
    handleChild: function (d) {
      this.age++;
      console.log("data from child", d);
    },
  },
};
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
