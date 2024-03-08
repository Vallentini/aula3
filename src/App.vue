<script setup>
//CONTADOR
import { ref, computed } from 'vue'
let contador = ref(0)
let contador2 = ref(0)
function incrementar() {
  contador.value++;
}

function decrementar() {
  if (contador.value > 0) {
    contador.value--;
  }
}
function reiniciar(
) {
  contador.value = 0;
}

function incrementar2() {
  contador2.value++;
}

function decrementar2() {
  if (contador2.value > 0) {
    contador2.value--;
  }
}
function reiniciar2(
) {
  contador2.value = 0;
}
const verificaParImpar = computed(() => { return soma() % 2 == 0 });

function soma() {
  return contador.value + contador2.value;
}
//FORMS INFORMAÇÃO
const nome = 'Vallentini'
const idade = 16

function inverter(texto) {
  return texto.split('').reverse().join('')
}

function saudacao() {
  return `Olá, ${nome}!`
}
const verdadeiroOuFalso = ref(true)
function mudaVerdadeiroOuFalso() {
  verdadeiroOuFalso.value = !verdadeiroOuFalso.value
}
const menor = '<div style="border-radius:20px; background-color: rgb(202, 59, 59); width: 500px; color:black; height: 30px; margin-top: 50px"><p style="margin-left:150px">---------------------------</p></div>';
const maior = '<div style="border-radius:20px; background-color: rgb(109, 231, 156); width: 500px; color:black; height: 30px; margin-top: 50px;"><p style="margin-left:150px">--------------------------</p></div>';
const par = '<div style="border-radius:20px; background-color: rgb(109, 231, 156); width: 500px; color:black; height: 30px; margin-top: 50px;"><p style="text-align: center">par</p>';
const impar = '<div style="border-radius:20px; background-color: rgb(202, 59, 59); width: 500px; color:black; height: 30px; margin-top: 50px;"><p style="text-align: center">impar</p>';
const verdadeiro = '<div style="border-radius:20px; background-color: rgb(109, 231, 156); width: 500px; color:black; height: 30px; margin-top: 50px;"><p style="text-align: center">verdadeiro</p>';
const falso = '<div style="border-radius:20px; background-color: rgb(202, 59, 59); width: 500px; color:black; height: 30px; margin-top: 50px;"><p style="text-align: center">falso</p>';
</script>

<template>

  <div class="info">
    <p class="text">O valor do contador 1 é: {{ contador }}</p>
    <button @click="incrementar">Incrementar</button>
    <button @click="decrementar">Decrementar</button>
    <button @click="reiniciar">Reiniciar</button>
    <p class="text">O valor do contador 2 é: {{ contador2 }}</p>
    <button @click="incrementar2">Incrementar</button>
    <button @click="decrementar2">Decrementar</button>
    <button @click="reiniciar2">Reiniciar</button>
    <div>
      <p>A soma é {{ soma() }}</p>
    </div>
    <span v-if="soma() > 10" v-html="maior"></span>
    <span v-if="soma() < 10" v-html="menor"></span>
    <span v-if="verificaParImpar" v-html="par"></span>
    <span v-if="!verificaParImpar" v-html="impar"></span>
    <span v-if="verdadeiroOuFalso == true" v-html="verdadeiro"></span>
    <span v-if="verdadeiroOuFalso == false" v-html="falso"></span>
    <button @click="mudaVerdadeiroOuFalso()">muda</button>
  </div>
</template>

<style scoped>
.info {
  background-color: rgb(30, 117, 98);
  padding: 20px 30px;
  color: white;
  border-radius: 10px;
  margin-right: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;

}

.text-forms {
  font-size: 20px;
  font-family: 'Times New Roman', Times, serif
}

button:hover {
  transform: scale(1.5);

}

button {
  background-color: cadetblue;
  height: 40px;
  margin-left: 10px;
  color: rgb(250, 250, 250);
  font-weight: bold;
  border-radius: 10px;
  transition: transform .3s;
  margin-left: 50px;
  margin-top: 50px;

}

.text {
  margin-top: 20px;
  font-family: "Madimi One", sans-serif;
  font-size: 20px;
  font-style: normal;
  font-weight: bold
}
</style>
