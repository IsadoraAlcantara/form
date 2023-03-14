<script setup>
import { ref } from'vue'
    const nome = 'Isadora'
    const idade = 15
    const contador = ref(0)

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function inverterMaiusculo(texto) {
        return texto.split('').reverse().join('').toUpperCase()
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }
</script>

<template>
    <div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverterMaiusculo(nome) }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>
    <div class="info">
      Contador: {{ contador }}
      <button @click="contador++">+</button>
      <button @click="contador--">-</button>
      <div v-if="contador > 10" class="vermelho">Maior que 10</div>
      <div v-else-if="contador < 10" class="verde">Menor que 10</div>
      <div v-else>É 10</div>
      <div v-show="contador % 2 == 0">Par</div>
    </div>
</template>

<style scoped>
.info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  margin: 0 15px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}

.vermelho {
  color: red;
}
.verde {
  color: green;
}
</style>
