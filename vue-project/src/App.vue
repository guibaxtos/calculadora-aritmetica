<script setup>
import { ref, computed } from "vue";

// Declarando variáveis reativas
const num1 = ref(0);
const num2 = ref(0);
const operation = ref("add");

// Computed para o resultado
const result = computed(() => {
  switch (operation.value) {
    case "add":
      return num1.value + num2.value;
    case "subtract":
      return num1.value - num2.value;
    case "multiply":
      return num1.value * num2.value;
    case "divide":
      return num2.value !== 0 ? num1.value / num2.value : "Divisão por zero!";
    default:
      return 0;
  }
});
</script>
<template>
  <div class="calculator">
    <h1>Calculadora Aritmética</h1>

    <div class="inputs">
      <input type="number" v-model.number="num1" placeholder="Número 1" />
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">×</option>
        <option value="divide">÷</option>
      </select>
      <input type="number" v-model.number="num2" placeholder="Número 2" />
    </div>

    <h2>Resultado: {{ result }}</h2>
  </div>
</template>
<style scoped>
.calculator {
  text-align: center;
  margin: 2em;
  font-family: Arial, sans-serif;
}

.inputs {
  margin: 1em 0;
}

input, select {
  margin: 0.5em;
  padding: 0.5em;
  font-size: 1rem;
}
</style>
