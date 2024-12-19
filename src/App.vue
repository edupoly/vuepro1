<script setup>
  import { ref } from 'vue';
  import Counter from './Counter.vue'
  import CounterReactive from './CounterReactive.vue'
  import Todolist from './Todolist.vue'
  var count = ref(123)
</script>

<template>
  <div class="m-3 p-2 border border-2">
    <Todolist></Todolist>
  </div>
  <!-- <Counter></Counter>
  <CounterReactive></CounterReactive>
  <br>
  <br> -->
</template>