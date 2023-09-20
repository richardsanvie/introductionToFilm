<script setup>
const nome = "Ya"

const pessoa = {
  nome: 'Yeyeye',
  age: 27,
} 

function darBoasVindas(nome){
  return `Seja bem vindo ${nome}!`
}

const imageRandom = 'https://source.unsplash.com/random/'

const btn = false
</script>

<template>
  <h1>{{ nome }}</h1>
  <p>{{ pessoa.nome }}</p>
  <p>{{ pessoa.age }}</p>
  <p>{{ darBoasVindas('Jo')}}</p>
  <img :src="imageRandom" alt="" style="width: 100px;">
  <button :disabled="!btn">Submeter</button>
</template>

<style scoped></style>
