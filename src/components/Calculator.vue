<template>
  <div class="calculator">
    <h1>Calculator App usig Vue.js</h1>
    <div class="display">
      <input id="output" v-model="total" />
    </div>

    <div id="buttons">
      <div class="buttons" v-on:click="button(1)">1</div>
      <div class="buttons" v-on:click="button(2)">2</div>
      <div class="buttons" v-on:click="button(3)">3</div>
      <div class="buttons" v-on:click="button('+')">+</div>
      <div class="buttons" v-on:click="button(4)">4</div>
      <div class="buttons" v-on:click="button(5)">5</div>
      <div class="buttons" v-on:click="button(6)">6</div>
      <div class="buttons" v-on:click="button('-')">-</div>
      <div class="buttons" v-on:click="button(7)">7</div>
      <div v-on:click="button(8)" class="buttons">8</div>
      <div class="buttons" v-on:click="button(9)">9</div>
      <div class="buttons" v-on:click="button('*')">*</div>
      <div class="buttons" v-on:click="button(0)">0</div>
      <div class="buttons" v-on:click="clear()">AC</div>
      <div class="buttons" v-on:click="calculation()">=</div>
      <div class="buttons" v-on:click="button('/')">/</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      total: '',
    };
  },
  methods: {
    button: function (num) {
      var z = "${num}";
      console.log(z);

      var x = num;
      return (this.total += x);
    },
    clear: function () {
      return (this.total = '');
    },
    calculation: function () {
      var equal = this.total;
      console.log(equal);
      return (this.total = eval(equal));
    },
  },
};
</script>

<style scoped>
body {
  font-family: "Open Sans", sans-serif;
  background-color: #4894d6;
}
body .calculator {
  background-color: #10B0A6;
  padding: 20px;
  margin: auto;
  width: 310px;
  clear: both;
  display: table;
  color:white;
}

body .display input {
  height: 36px;
  width: 90%;
  font-size: 20px;
  font-weight: bold;
  border-radius: 4px;
  margin: 0 0 14px 0;
  
  padding: 0 1em;
  box-size: border-box;
}

body #buttons div {
  cursor: pointer;
  width: 66px;
  height: 36px;
  font-weight: bold;
  text-align: center;
  line-height: 2em;
  background: #1D2221;
  border-radius: 3px;
  
  margin:3px;
  float: left;
}
</style>
