<script setup>
import { ref, computed } from 'vue'

const tareas = ref([
  { texto: 'Estudiar Vue.js', completada: true },
  { texto: 'Hacer mi tarea', completada: false },
  { texto: 'Lavar mi auto', completada: true },
  { texto: 'Sacar a mi perro', completada: false }
])

const tareasCompletadas = computed(() => {
  return tareas.value.filter(tarea => tarea.completada)
})
</script>

<template>
    <h1>Ejercicio 2</h1>
    <div class="p-4 border rounded shadow-md max-w-md mx-auto mt-10">
        <h2 class="text-xl font-bold mb-4">Tareas Completadas</h2>

        <ul class="list-disc pl-5">
        <li v-for="(tarea, index) in tareasCompletadas" :key="index">
            {{ tarea.texto }}
        </li>
        </ul>
    </div>
</template>