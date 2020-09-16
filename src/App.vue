<template>
  <div id="app">
    <h1>Math Quiz App</h1>
    <OperatorQuiz @onBack="clearOperator" v-if="operator" :operator="operator" />
    <OperatorSelector v-if="!operator" @changeOperator="changeOperator" />
  </div>
</template>

<script>
import OperatorSelector from "./components/OperatorSelector";
import OperatorQuiz from "./components/OperatorQuiz";

export default {
  name: "App",
  data() {
    return {
      operator: null,
    };
  },
  methods: {
    changeOperator(operator) {
      this.operator = operator;
    },
    clearOperator() {
      this.operator = null;
    },
  },
  components: { OperatorSelector, OperatorQuiz },
};
</script>
  
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 20px;
}

button {
  padding: 10px;
  width: 140px;
  margin-right: 10px;
  height: 80px;
  background-color: #042a10;
  color: lightgray;
  font-size: 20px;
  cursor: pointer;
  vertical-align: top;
}
</style>
