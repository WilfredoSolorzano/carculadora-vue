<script setup>
import { ref, computed } from 'vue';
import InputEntrada from './components/InputEntrada.vue';
import InputSegundaEntrada from './components/InputSegundaEntrada.vue';
import Resultado from './components/Resultado.vue';

const num1 = ref(0);
const num2 = ref(0);
const operation = ref('add');

const result = computed(() => {
  switch (operation.value) {
    case 'add':
      return num1.value + num2.value;
    case 'subtract':
      return num1.value - num2.value;
    case 'multiply':
      return num1.value * num2.value;
    case 'divide':
      return num2.value !== 0 ? num1.value / num2.value : 'Erro: Divisão por zero';
    default:
      return 0;
  }
});
</script>

<template>
  <div id="app" class="container">
    <h1 class="my-4">Calculadora Aritmética</h1>
    <div class="row mb-3">
      <InputEntrada :num1="num1" @update:num1="num1 = $event" />
      <InputSegundaEntrada :num2="num2" :operation="operation" @update:num2="num2 = $event" @update:operation="operation = $event" />
    </div>
    <Resultado :result="result" />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
input, select {
  margin: 10px;
}
</style>