  <script setup>
  import { ref, computed } from 'vue';
  
  const num1 = ref(0);
  const num2 = ref(0);
  const operacao = ref('+');
  
  const resultado = computed(() => {
    switch (operacao.value) {
      case '+':
        return num1.value + num2.value;
      case '-':
        return num1.value - num2.value;
      case '*':
        return num1.value * num2.value;
      case '/':
        return num2.value !== 0 ? num1.value / num2.value : 'Erro: Divisão por zero';
      default:
        return 0;
    }
  });
  </script>
<template>
    <div class="calculadora">
      <div class="input-group mb-3">
        <input type="number" class="form-control" v-model.number="num1" placeholder="Número 1">
        <select class="form-select" v-model="operacao">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
        <input type="number" class="form-control" v-model.number="num2" placeholder="Número 2">
      </div>
      <h3>Resultado: {{ resultado }}</h3>
    </div>
  </template>
  
  
  <style scoped>
  .calculadora {
    max-width: 400px;
    margin: auto;
    padding: 20px;
    border: 3px solid #184098;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    background-color: aqua;
  }
  .input-group {
    display: flex;
  }
  </style>
  