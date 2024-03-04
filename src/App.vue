<script setup>
//CONTADOR
import{ref} from 'vue'
let contador = ref(0)
let contador2 = ref(0)
 function incrementar() {
    contador.value++;
  }

function decrementar(){
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

function decrementar2(){
  if (contador2.value > 0) {
      contador2.value--;
    }
  }
function reiniciar2(
) {
  contador2.value = 0;
}

function soma() {
  contador.value + contador2.value;
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
const menor = '<div style="border-radius:20px; background-color: rgb(202, 59, 59); width: 500px; color:black; height: 30px; margin-top: 50px"><p style="margin-left:150px">maior que 10 é red</p></div>'
const maior = '<div style="border-radius:20px; background-color: rgb(109, 231, 156); width: 500px; color:black; height: 30px; margin-top: 50px;"><p style="margin-left:150px">menor que 10 é verdin </p></div>'
</script>

<template>

  <div class="info">
    <h1>Exemplo 1 - Mostrando informações na tela</h1>
    <p class="text-forms">Nome: {{ nome }} </p>
    <p class="text-forms">Idade: {{ idade }} anos</p>
    <hr />
    <p class="text-forms">Para completar 50 anos faltam: {{ 50 - idade }} anos</p>
    <p class="text-forms">O nome tem {{ nome.length }} caracteres</p>
    <p class="text-forms">O nome invertido é: {{ inverter(nome).toUpperCase() }} </p>
    <hr />
    <p class="text-forms"> Exemplo de saudação usando função</p>
    <p class="text-forms"> {{ saudacao() }} </p>
  </div>

  <div class="info">
    <p class="text">O valor do contador 1 é: {{ contador }}</p>
    <button @click="incrementar">Incrementar</button>
    <button @click="decrementar">Decrementar</button>
    <button @click="reiniciar">Reiniciar</button>
    <p class="text">O valor do contador 2 é: {{ contador2 }}</p>
    <button @click="incrementar2">Incrementar</button>
    <button @click="decrementar2">Decrementar</button>
    <button @click="reiniciar2">Reiniciar</button>
    <div> <p>A soma é {{ soma }}</p></div>
    <div v-if="contador > 10 " v-html="maior" ></div>
  <div v-else v-html="menor"></div>
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
  font-family:'Times New Roman', Times, serif
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
