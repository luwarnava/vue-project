<template>
  <div id="app" class="calculator">
    <h1>Calculadora Aritmética</h1>
    <div class="inputs">
      <input 
        type="number" 
        v-model.number="num1" 
        placeholder="Digite o primeiro número"
      />
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">×</option>
        <option value="divide">÷</option>
      </select>
      <input 
        type="number" 
        v-model.number="num2" 
        placeholder="Digite o segundo número"
      />
    </div>
    <div class="result">
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: "add",
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case "add":
          return this.num1 + this.num2;
        case "subtract":
          return this.num1 - this.num2;
        case "multiply":
          return this.num1 * this.num2;
        case "divide":
          return this.num2 !== 0 ? this.num1 / this.num2 : "Erro: Divisão por zero";
        default:
          return 0;
      }
    },
  },
};
</script>

<style>
.calculator {
  font-family: Arial, sans-serif;
  text-align: center;
  margin: 20px;
}

.inputs {
  margin: 20px;
}

.inputs input, .inputs select {
  margin: 5px;
  padding: 10px;
  font-size: 16px;
}

.result h2 {
  color: #007BFF;
}
</style>
