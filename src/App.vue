<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: '+',
      resultado: 0
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case '+':
          this.resultado = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case '-':
          this.resultado = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case '*':
          this.resultado = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case '/':
          this.resultado = parseFloat(this.num1) / parseFloat(this.num2);
          break;
      }
    }
  }
};
</script>

<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>

    <input type="number" v-model="num1" @input="calcular" />
    <select v-model="operacao" @change="calcular">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">x</option>
      <option value="/">/</option>
    </select>
    <input type="number" v-model="num2" @input="calcular" />

    <p>Resultado: {{ resultado }}</p>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 20px;
}

input,
select {
  margin: 10px;
  padding: 5px;
}
</style>
