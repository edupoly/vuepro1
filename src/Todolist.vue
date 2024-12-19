<script setup>
import { reactive } from "vue";
import Todo from './Todo.vue'
    var state = reactive({
        todos:[
            {
                title:'new car',
                status:false
            },
            {
                title:'pay rent',
                status:false
            },
            {
                title:'get tea',
                status:true
            }
        ]
    })
    function add(){
        state.todos.push({title:document.getElementById("d1").value,status:false})
    }
    function toggle(i){
        state.todos[i].status=!state.todos[i].status;
    }
</script>
<template>
    <input type="text" id="d1">
    <button @click="add">Add Todo</button>
    <ul>
        <div v-for="(todo,i) in state.todos" :key="i">
            <Todo :todo="todo" :i="i" :toggle="toggle"></Todo>
        </div>
    </ul>
</template>