<script setup>
import { ref, computed } from 'vue'

const nome = ref('')
const email = ref('')
const senha = ref('')
const senhaConfir = ref('')
const nascimento = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const hobbies = ref('')
const biografia = ref('')
const linguagem = ref('')
const confirmacao = ref(false)

const confirma = computed(() => {
  if (email.value.includes("@") && nome.value.length >= 3 && nome.value.length <= 20 && senha.value == senhaConfir.value) {
    confirmacao.value = true
  }
})

</script>

<template>
<form @submit.prevent="">
<p>nome:</p><input type="text" v-model="nome" />
<p>email</p><input type="email" v-model="email" />
<p>senha</p><input type="password" v-model="senha" />
<p>senha de confirmação</p><input type="password" v-model="senhaConfir" />
<p>data de nascimento</p><input type="date" v-model="nascimento" />
<p>endereço</p><input type="text" v-model="endereco" />
<p>cidade</p><input type="text" v-model="cidade" />
<p>estado</p>

  <select v-model="estado">
    <option value="AC">Acre</option>
    <option value="AL">Alagoas</option>
    <option value="AP">Amapá</option>
    <option value="AM">Amazonas</option>
    <option value="BA">Bahia</option>
    <option value="CE">Ceará</option>
    <option value="DF">Distrito Federal</option>
    <option value="ES">Espírito Santo</option>
    <option value="GO">Goiás</option>
    <option value="MA">Maranhão</option>
    <option value="MS">Mato Grosso</option>
    <option value="MS">Mato Grosso do Sul</option>
    <option value="MG">Minas Gerais</option>
    <option value="PA">Pará</option>
    <option value="PB">Paraíba</option>
    <option value="PR">Paraná	</option>
    <option value="PE">Pernambuco</option>
    <option value="PI">Piauí</option>
    <option value="RJ">Rio de Janeiro</option>
    <option value="RN">Rio Grande do Norte</option>
    <option value="RS">Rio Grande do Sul </option>
    <option value="RO">Rondônia</option>
    <option value="RR">Roraima</option>
    <option value="SC">Santa Catarina </option>
    <option value="SP">São Paulo</option>
    <option value="SE">Sergipe</option>
    <option value="TO">Tocantins</option>
  </select>
<p>hobbies</p>
  <textarea v-model="hobbies" />
  <p style="white-space: pre-line;"></p>

  <p>biografia</p>
  <textarea v-model="biografia" />
  <p style="white-space: pre-line;"></p>

  <p>linguagens de programação</p>
  <textarea v-model="linguagem" />
  <p style="white-space: pre-line;"></p>

</form>

<div><button type='submit' @click="confirma" class="botao">enviar</button></div>

<div v-if="confirma === true ">
<p>Nome: {{ nome }}</p>
<p>Email: {{ email }}</p>
<p>Senha: {{ senha }}</p>
<p>Data de nascimento: {{ nascimento }}</p>
<p>Endereço: {{ endereco }}</p>
<p>Cidade: {{ cidade }}</p>
<p>Estado: {{ estado }}</p>
<p>hobbies: {{ hobbies }}</p>
<p>biografia: {{ biografia }}</p>
<p>Linguagens de programação: {{ linguagem }}</p>
</div>


</template>

<style scoped>

.botao{
  font-size: 20px;
  background-color: black;
  color: aliceblue;
  border-radius: 8px;
  margin: none;
}
</style>
