<script setup>
import { reactive } from "vue";

    var state = reactive({count:0})
    console.log(state)
    function inc(){
        state.count++;
    }
</script>
<template>
    <h1>Counterruuu:{{state.count}}</h1>
    <button @click="inc">Incre</button>
</template>