<script setup>
import { reactive } from 'vue';

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

// containerContador

const estado = reactive({
  contador: 0,
  email: 0,
  saldo: 5000,
  transferindo: 0,
  nomes: ['Jo', 'Ye', 'He'],
  nomeAInserir: ''

})


function incrementar() {
  estado.contador++;
}

function decrementar() {
  estado.contador--;
}

// containerEmail

function alteraEmail(evento) {
  estado.email = evento.target.value
}

// containerBank

function mostraSaldoFuturo() {
  return estado.saldo - estado.transferindo;
}

function validaValor() {
  return estado.saldo >= estado.transferindo;
}

// List names

function cadastrarNome() {
  if (estado.nomeAInserir.length >= 3) {
    estado.nomes.push(estado.nomeAInserir)
  } else {
    alert("Digite mais caracteres")
  }
}


</script>

<template>
  <div class="containerLise">
    <ul>
      <li v-for="listnames in estado.nomes">{{ listnames }}</li>
    </ul>
    <input type="text" placeholder="Insere novo nome" @keyup="evento7 => estado.nomeAInserir = evento7.target.value">
    <button @click="cadastrarNome">Inserir</button>
  </div>

  <hr>

  <div class="containerBank">
    <p>Saldo: {{ estado.saldo }}</p>
    <p>Transferindo: {{ estado.transferindo }}</p>
    <p>Saldo após a transfêrencia: {{ mostraSaldoFuturo() }}</p>
    <input :class="{ invalido: !validaValor() }" type="number"
      @keyup="evento1 => estado.transferindo = evento1.target.value">
    <button v-if="validaValor()">Transferir</button>
    <span v-else>Saldo insuficiente</span>
  </div>
  <hr>
  <div class="containerEmail">
    <input type="email" @keyup="alteraEmail">
    <p>{{ estado.email }}</p>

  </div>
  <hr>
  <div class="containerContador">
    <p>{{ estado.contador }}</p>
    <button @click="incrementar">+</button>
    <button @click="decrementar">-</button>
  </div>
  <hr>
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

.invalido {
  outline-color: red;
  border-color: red;
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
