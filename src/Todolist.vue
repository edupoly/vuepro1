<script setup>

import { reactive, watch } from "vue";
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
        ],
        newtodo:'',
        gender:'',
        techs:[]
    })
    function add(){
        state.todos.push({title:state.newtodo,status:false})
    }
    function toggle(i){
        state.todos[i].status=!state.todos[i].status;
    }
    watch(state,()=>{console.log("Hello")})
</script>
<template>
    <input v-model="state.newtodo">
    <button @click="add">Add Todo</button>
    <br>
    <input type="checkbox" v-model="state.techs" value='rjs'>:ReactJS
    <input type="checkbox" v-model="state.techs" value='njs'>:NodeJS
    <input type="checkbox" v-model="state.techs" value='vjs'>:VueJS
    <input type="checkbox" v-model="state.techs" value='ajs'>:Angular
    <input type="checkbox" v-model="state.techs" value='nxtjs'>:NextJS
    <h2>{{state.techs}}</h2>
    <ul>
        <div v-for="(todo,i) in state.todos" :key="i">
            <Todo :todo="todo" :i="i" :toggle="toggle"></Todo>
        </div>
    </ul>
</template>
// <input type="radio" v-model="state.gender" value="m">:Male
//     <input type="radio" v-model="state.gender" value="f">:Female
//     <input type="radio" v-model="state.gender" value="o">:Others
//     <h1>{{state.gender}}</h1>