<template>
    <!-- <div style="width:500px">
        <input type="text" style="width: 80%;">
    </div> -->
    <div id="bgc1"></div>
    <div id="bgc2"></div>
    <h1>My To-do list</h1>
    <div id="input">
        <input type="text" v-model="newtodo">
        <button id="button" v-on:click='addTodo'>add todo's</button>
    </div>
    <div id='list'>
        <ul>
            <li v-for="todo in todolist">{{ todo.title }}</li>
        </ul>
    </div>
</template>

<script  setup>

import { ref } from 'vue'
const todolist = ref([])
const newtodo = ref('')
const addTodo = () => {
    const todo = {
        title: newtodo.value,
        isDone: false
    }
    todolist.value.push(todo)
}
</script>

<style >
h1 {
    margin-top: 20px;
    text-align: center;
    color: #fff;
    font-size: 50px;
    letter-spacing: 0px;
    transition: 2s;
}

h1:hover {
    letter-spacing: 15px;
}

#app {
    display: flex;
    justify-content: center;
    align-items: center;
}

input {
    border-radius: 5px;

    width: 80%;
    height: 35px;
    border: 1px solid silver;
    /* box-shadow: 2px 2px black; */

}

#button {
    height: 35px;
    border-radius: 5px;
    /* margin:0 25px; */
    float: right;
    border: 0cap;

}

button {
    background-color: rgb(255, 43, 149);
    color: white;

}

#bgc1 {
    background-color: rgb(255, 43, 149);
    width: 100%;
    height: 25%;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: -1;
}

#bgc2 {
    background-color: white;
    width: 100%;
    height: 75%;
    position: fixed;
    top: 25%;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: -2;
}

body {
    display: inline;
}

#input {
    /* width: 90%;
     margin: auto; */
    margin-top: 25%;
    background-color: #fff;
    padding: 10px;
    border-radius: 5px;
    box-shadow: 0px 10px 15px -3px rgba(0, 0, 0, 0.1);

}

main {
    width: 50%;
    height: 50%;
}


#list {
    margin-top: 30px;
}



#list li {
    border: 2px solid gray;
    margin: 5px;
    height: 50px;
    border-radius: 5px;
    background-color: #fff;
    padding-left: 5px;
    padding-top: auto;
    transition: 1s;


}

#list li:hover {
    background-color: pink;
    color: white;
}

ul {
    list-style-type: none;
    padding: 0;
}
</style>