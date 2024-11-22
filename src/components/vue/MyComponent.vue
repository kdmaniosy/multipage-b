<script setup>
import { ref } from 'vue'

const name = "Pepito"
let counter = ref(5)

let characters = ref([])

function add(){
    counter.value++
    characters.value.push(counter.value)
}
function rest(){
    counter.value--
    console.log(counter)
}

console.log("Hola mundo", name)

</script>


<template>
    <div class="mx-auto max-w-96 rounded bg-blue-300 py-4 px-6">
        Hola {{ name }}
        <div v-if="counter > 0" class="size-8 text-white bg-red-600 rounded-full flex items-center justify-center">
            {{ counter }}
        </div>
        <div v-else>
            Nadie te escribe 😢
        </div>
        <div @click="add()" class="size-8 text-white bg-blue-600 rounded-full flex items-center justify-center">
            +
        </div>
        <div @click="rest()" class="size-8 text-white bg-green-600 rounded-full flex items-center justify-center">
            -
        </div>
    </div>
    <div v-for="(name, index) in characters" :key="index" class="bg-green-500 mb-1">
        {{ name }}
    </div>

</template>