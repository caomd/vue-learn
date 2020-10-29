<template>
  <div>child components {{ name }} age{{age}}
  <slot name="b"></slot>

  <button @click="$emit('patch',45)">发送到父组件</button>
  <slot name="a"></slot>
  </div>
</template>
<script>
export default {
  props:['age',],  
  data: function () {
    return {
      name: "com",
    };
  },
};
</script>