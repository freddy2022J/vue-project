<template>
  <div>
    <h1>Calculator</h1>
    <input type="number" v-model="number1" />
    <select v-model="selectedOperation">
      <option value="addition">+</option>
      <option value="subtraction">-</option>
      <option value="multiplication">*</option>
      <option value="division">/</option>
    </select>
    <input type="number" v-model="number2" />
    <button @click="calculate()">Calculate</button>
    <h2>Result: {{ result }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: null,
      number2: null,
      selectedOperation: "addition",
      result: null
    };
  },
  methods: {
    calculate() {
      switch (this.selectedOperation) {
        case "addition":
          this.result = this.number1 + this.number2;
          ;
        case "subtraction":
          this.result = this.number1 - this.number2;
          break;
        case "multiplication":
          this.result = this.number1 * this.number2;
          break;
        case "division":
          this.result = this.number1 / this.number2;
          break;
        default:
          this.result = null;
          break;
      }
    }
  }
};
</script>
