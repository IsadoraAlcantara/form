<script setup>
import { ref, computed } from 'vue'

const contador1 = ref(0)
const contador2 = ref(0)
const soma = computed(() => contador1.value + contador2.value)
/* function soma() {
  return contador1.value + contador2.value
} */
const mostrar = ref(true)

</script>

<template>
  <div class="container">
    <button class="btn btn-primary" @click="mostrar = !mostrar">Mostrar / Esconder</button>
    <div v-if="mostrar">
      <div>
        <button class="btn btn-primary" @click="contador1--">-</button>
        <span class="mx-3 fs-4">{{ contador1 }}</span>
        <button class="btn btn-primary" @click="contador1++">+</button>
      </div>
      <div>
        <button class="btn btn-primary" @click="contador2--">-</button>
        <span class="mx-3 fs-4">{{ contador2 }}</span>
        <button class="btn btn-primary" @click="contador2++">+</button>
      </div>
      <div>
        <p class="fs-3">A soma é {{  soma  }}</p>
        <p v-if="soma > 10" class="fs-3">A soma é maior que 10</p>
        <p v-else class="fs-3">A soma é menor ou igual a 10</p>
      </div>
      <p v-if="soma % 2 === 0" class="fs-3">A soma é par</p>
      <p v-else class="fs-3">A soma é ímpar</p>
    </div>
  </div>
</template>

<style scoped></style>
