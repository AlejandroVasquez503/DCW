<script setup>
import { ref, computed } from 'vue'

const precio = ref(0)
const descuento = ref(0)

const precioFinal = computed(() => {
  return precio.value - (precio.value * descuento.value / 100)
})

</script>

<template>
    <h1>Ejercicio 1</h1>
    <div class="p-4 border rounded shadow-md max-w-md mx-auto mt-10">
    <h2 class="text-xl font-bold mb-4">Calculadora de Descuento</h2>

    <label class="block mb-2">
      Precio original:
      <input v-model.number="precio" type="number" class="border px-2 py-1 w-full" />
    </label>

    <label class="block mb-2">
      Porcentaje de descuento:
      <input v-model.number="descuento" type="number" class="border px-2 py-1 w-full" />
    </label>

    <p class="mt-4 font-semibold">Precio final: ${{ precioFinal.toFixed(2) }}</p>
  </div>
</template>