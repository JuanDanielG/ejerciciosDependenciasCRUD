<script setup>
import { ref } from 'vue'

const todos = ref(['Estudiar bastante'])
const todo = ref('')

function add () {
    // console.log(todo.value)
    todos.value.unshift(todo.value)
    todo.value = ''
}

</script>

<template>
    <div class="py-6 px-5 rounded shadow bg-slate-200 max-w-96 mx-auto mt-12">
        <div>
            <input v-model="todo" class="px-2 w-4/5 outline-none rounded  " />
            <button 
            @click="add"  
            class="w-1/5 bg-orange-300 text-white text-center rounded" >+</button>

        </div>
        <div class="mt-3">
            <div v-for="(todo, i) in todos" :key="i" class=" bg-red-100 rounded px-2 py-1 flex justify-between mb-2" > {{ todo }}
                <div class="space-x-1">
                    <button class="bg-red-600 outline-none text-white tex-center rounded py-1 px-1">Borrar</button>
                    <button class="bg-yellow-200 outline-none text-white tex-center rounded py-1 px-1" >Editar</button>
                </div>
            </div>
        </div>
    </div>
</template>