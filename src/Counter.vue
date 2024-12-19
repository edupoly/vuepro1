<script setup>
    import {ref} from 'vue'
    const count = ref(1)
    function inc(){
        count.value++;
    }
</script>
<template>
    <h2>Counter:{{count}}</h2>
    <button @click="inc">Increment</button>
</template>