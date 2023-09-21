<script setup>
const nome = "Ya"

const pessoa = {
  nome: 'Yeyeye',
  age: 27,
}

function darBoasVindas(nome) {
  return `Seja bem vindo ${nome}!`
}

const imageRandom = 'https://source.unsplash.com/random/'


const btn = false

const blueContainer = false
const greenContainer = false


</script>

<template>
  <h1>{{ nome }}</h1>
  <p>{{ pessoa.nome }}</p>
  <p>{{ pessoa.age }}</p>
  <p>{{ darBoasVindas('Jo') }}</p>
  <div class="container">
    <img :src="imageRandom" id="img">
    <button :disabled="!btn">Submeter</button>
  </div>

  <div class="container2">
    <div class="containerIntern" v-if="blueContainer">
    </div>
    <div class="containerIntern1" v-else-if="greenContainer">
    </div>
    <div v-else class="containerIntern2">    
      <img :src="imageRandom" id="img">
    </div>
  </div>
</template>

<style scoped>
.container {
  background-color: aquamarine;
  text-align: center;
  align-items: center;
  display: flex;
  flex-direction: column;
}

#img {
  margin-bottom: 10px;
  width: 100px;
}

.container2 {
  display: flex;
  background-color: bisque;
}

.containerIntern {
  width: 50%;
  height: 200px;
  background-color: blue;
}

.containerIntern1 {
  width: 50%;
  height: 200px;
  background-color: rgb(0, 255, 42);
}

.containerIntern2 {
  width: 50%;
  height: 200px;
  background-color: rgb(255, 0, 170);
}


.containerIntern3 {
  width: 50%;
  height: 200px;
  background-color: rgb(255, 145, 0);
}
</style>
