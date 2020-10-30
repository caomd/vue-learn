<template>
  <div class="pageb">PageB{{ $store.state.count.count }}
         <button @click="add(5)">增加</button>
      <button @click="reduce">减少</button>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
    methods: mapActions('count',['add','reduce'])
};
</script>

<style>
</style>