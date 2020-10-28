<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div v-html="msg1" v-bind:id="id"></div>
    <div>{{ number + 1 }}</div>
    <div v-if="seen">你看见我</div>
    <div v-n="6"></div>
    <div :class="[a1, a2]">我借你{{ money }},你还我{{ a }},我还剩下{{ b }}</div>
    <div :class="{ 'test-1': a3 }">style object</div>
    <div :class="obj">style obj</div>
    <ul>
      <li v-for="item in list" :key="item">{{ item }}</li>
    </ul>
    <ul>
      <template v-for="item in list">
        <li :key="item + 1">hello</li>
        <li :key="item">{{ item }}</li>
      </template>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      msg1: '<span style="color:red;">Hello world</span>',
      id: "txt",
      number: 1,
      seen: true,
      money: 1000,
      a: 10,
      a1: "test-1",
      a2: "test-2",
      a3: false,
      obj: {
        "text-1": true,
      },
      list: ["a", "b", "c", "d"],
    };
  },
  computed: {
    b: function () {
      return this.money - this.a;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
