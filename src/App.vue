<script setup>
import { reactive } from 'vue';
import Calculadora from './components/Calculadora.vue';

const estado = reactive({
  operacao: 'Somar',
  campoNum1: 0,
  campoNum2: 0,
})

const somar = (num1, num2) => num1 + num2;
const subtrair = (num1, num2) => num1 - num2;
const dividir = (num1, num2) => num1 / num2;
const multiplicar = (num1, num2) => num1 * num2;

const getOperacao = () => {
  const { operacao } = estado;

  switch (operacao) {
    case 'Somar':
      return somar(estado.campoNum1, estado.campoNum2);
    case 'Subtrair':
      return subtrair(estado.campoNum1, estado.campoNum2);
    case 'Dividir':
      return dividir(estado.campoNum1, estado.campoNum2);
    case 'Multiplicar':
      return multiplicar(estado.campoNum1, estado.campoNum2);
  }
}

</script>

<template>
  <div class="container">
    <Calculadora :seleciona-operacao="evento => estado.operacao = evento.target.value" :captura-num1="evento => estado.campoNum1 = parseFloat(evento.target.value)" :captura-num2="evento => estado.campoNum2 = parseFloat(evento.target.value)" :renderiza-resultado="getOperacao()" />
  </div>

</template>

<style scoped>
.container {
    max-width: 600px;
    width: 100%;
    margin: 0 auto;
}
</style>