<template>
  <div>
    <button @click="msg('sdd', $event)">test</button>
    <div class="parent" @click="parent">
        <p>parent</p>
        <p>parent</p>
        <p>parent</p>
        <div class="children" @click.stop="child">
            child
        </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ev",
  data() {
    return {
      counter: 0,
    };
  },
  methods: {
    msg: function (s, b) {
      alert(s);
      console.log(b);
    },
    parent: function(){
        window.console.log('parent')
    },
    child: function(){
        window.console.log('child')

    }
  },
};
</script>
<style scoped>
</style>