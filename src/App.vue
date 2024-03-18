<template>
  <div class="calculator">
    <input type="number" v-model="num1" @input="calculate">
    <select v-model="operator" @change="calculate">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input type="number" v-model="num2" @input="calculate">
    <div class="result">Resultado: {{ result }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case '+':
          this.result = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case '-':
          this.result = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case '*':
          this.result = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case '/':
          this.result = parseFloat(this.num1) / parseFloat(this.num2);
          break;
      }
    }
  }
};
</script>

<style scoped>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
}

input[type="number"] {
  width: 100px;
  margin: 5px;
  padding: 5px;
}

select {
  width: 100px;
  margin: 5px;
  padding: 5px;
}

.result {
  margin-top: 10px;
  font-weight: bold;
}
</style>
