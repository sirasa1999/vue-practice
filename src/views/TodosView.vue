<template>
  <div id="app" class="w-1/2 mx-auto p-4 bg-purple-900 rounded-md m-12 relative overflow-hidden pt-14 mt-20">
    <div class="w-full absolute bg-gray-700 top-0 right-0 left-0 text-center text-white font-semibold text-xl py-2">
      <h1>TODO List</h1>
    </div>
    <form @submit.prevent='addNewTodo()' class="border-b-2 border-purple-300" py-4>
      <div>
        <input v-model='newTodo' type="text" class="flex-1 w-full px-2 py-1 rounded-2xl text-gray-600 focus:outline-none">
      </div>
      <div class="mt-5 mb-3 flex items-center justify-between">
        <button class="px-3 py-2 rounded-xl bg-gray-600 hover:bg-gray-500 text-white">
          Add Todo
        </button>
        <button class="hover:bg-gray-800 text-white">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 hover:w-7 h-7">
          <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12c0 1.268-.63 2.39-1.593 3.068a3.745 3.745 0 01-1.043 3.296 3.745 3.745 0 01-3.296 1.043A3.745 3.745 0 0112 21c-1.268 0-2.39-.63-3.068-1.593a3.746 3.746 0 01-3.296-1.043 3.745 3.745 0 01-1.043-3.296A3.745 3.745 0 013 12c0-1.268.63-2.39 1.593-3.068a3.745 3.745 0 011.043-3.296 3.746 3.746 0 013.296-1.043A3.746 3.746 0 0112 3c1.268 0 2.39.63 3.068 1.593a3.746 3.746 0 013.296 1.043 3.746 3.746 0 011.043 3.296A3.745 3.745 0 0121 12z" />
</svg>
</button>
      </div>
    </form>

    <div id="todos" class="space-y-4 my-4 text-white">
      <div id="todo" v-for="todo in todos" :key="todo.id" @click="todoCompleted(todo)" class="px-2 py-3 rounded-lg bg-purple-700 cursor-pointer transform hover:scale-105 transition duration-500 ease-in-out flex item-center justify-between"
      :class="{'bg-purple-500 text-zinc-500 line-through': todo.isCompleted}">
      <h1>{{todo.text}}</h1>
      <span class="">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 hover:w-7 h-7" fill="none">
        <path stroke-linecap="round" stroke-linejoin="round" d="M14.74 9l-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 01-2.244 2.077H8.084a2.25 2.25 0 01-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 00-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 013.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 00-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 00-7.5 0" />
      </svg>
</span>
    </div>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue'

    const newTodo=ref('')
    const todos=ref([
      {
        id:1,
        text:'Drinking Water',
        isCompleted: false
      },
      {
        id:2,
        text:'Drinking juice',
        isCompleted: true
      },
    ])

    function addNewTodo(){
      console.log(newTodo.value);
    }

</script>
