<script setup>
    var state = defineProps(['todo',"i","toggle"])
    var {todo,i,toggle}=state
</script>
<template>
 
    <li :class="todo.status?'bg-success m-2 p-2':'bg-danger m-2 p-2'" :style="todo.status?{color:'white'}:{color:'black'}">
        <b v-if="todo.status">
            {{todo.title}}
            <button @click="()=>{toggle(i)}">Undo</button>
        </b>
        <i v-if="!todo.status">
            {{todo.title}}
            <button @click="()=>{toggle(i)}">Done</button>
        </i>
        <button>Delete</button>
    </li>
 
</template>