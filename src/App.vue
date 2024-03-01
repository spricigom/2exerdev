<script setup>
  const nome = 'Emili'
  const idade = 16

  function inverter (texto){
    return texto.split('').reverse().join('').toUpperCase()
  }

  function saudacao (){
    return `Olá, ${nome} `
  }

import { ref } from 'vue';
const contador = ref (0)
function decrementar(){
  if (contador.value > 0){
    contador.value--
  }
}

function reiniciar(){
  contador.value = 0;
}

</script>

<template>
  <div class="info">
    <h1>Exemplo 1 - Mostrando informações na tela</h1>
    <p>Nome: {{ nome }}</p>
    <p>Idade: {{ idade }} anos</p>
    <hr />
    <p>Para completar 50 anos faltam: {{ 50 - idade }} anos</p>
    <p>O nome tem {{ nome.length }} caracteres</p>
    <p>O nome invertido é {{ inverter(nome) }}</p>
    <hr />
    <p>Exemplo de saudação usando função:</p>
    <p>{{ saudacao() }}</p> 
  </div>

  <div class="conta">
  <h1>Contador</h1>
    <button @click="contador++">Adicionar</button>
    <button @click="decrementar">Subtrair</button>
    <button @click="reiniciar">Reiniciar</button>
    <p>valor do contador : {{ contador }}</p>
    <div
      :style="{ backgroundColor: contador > 10 ? 'green'  : 'red' }"
    >
      <p v-if="contador > 10">Valor maior que 10</p>
      <p v-else>Valor menor que 10</p>
    </div>
  </div>
</template>

<style scoped>
  .info{
    background-color: plum;
    padding: 20px 30px;
    color: black;
    border-radius: 10px;
  }
  .conta{
    background-color: lightskyblue;
    padding: 20px 30px;
    color: black;
    border-radius: 10px;
  }
  button{
    background-color: lightskyblue;
    color: black;
    border-radius: 3px;
    border-color: black;
    margin: 2px;
    padding: 5px;
  }
  h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
</style>