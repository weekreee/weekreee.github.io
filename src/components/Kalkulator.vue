<template>
    <div>
      <h1> Kalkulator Sederhana </h1>
      <div class="calculator">
        <input type="text" class="screen" v-model="display" placeholder="0">
  
        
        <button class="number" @click="() => show('1')">1</button>
        <button class="number" @click="() => show('2')">2</button>
        <button class="number" @click="() => show('3')">3</button>
        <button class="symbol" @click="wipe">AC</button>
  
        <button class="number" @click="() => show('4')">4</button>
        <button class="number" @click="() => show('5')">5</button>
        <button class="number" @click="() => show('6')">6</button>
        <button class="symbol" @click="() => show('+')">+</button>
        
        <button class="number" @click="() => show('7')">7</button>
        <button class="number" @click="() => show('8')">8</button>
        <button class="number" @click="() => show('9')">9</button>
        <button class="symbol" @click="() => show('-')">-</button>
        
        <button class="symbol" @click="() => show('*')">*</button>
        <button class="number" @click="() => show('0')">0</button>
        <button class="symbol" @click="() => show('/')">/</button>
        <button class="symbol" @click="calc">=</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Kalkulator',
    data() {
      return {
        display: '',
      };
    },
    methods: {
      wipe() {
        this.display = '';
      },
      show(n) {
        this.display += n;
      },
      calc() {
        this.display = eval(this.display);
      },
    },
  };
  </script>
  
  <style>
  .calculator {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
    max-width: 300px;
    margin: 0 auto;
    margin-top: 20px;
    text-align: center;
  }

  .screen {
    grid-column: span 4;
    height: 40px;
    font-size: 1.5em;
    text-align: right;
    padding: 10px;
    margin-bottom: 10px;
  }

  button {
    height: 40px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #f9f9f9;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  button:hover {
    background-color: #e9e9e9;
  }

  .symbol {
    background-color: #f2a154;
  }

  .number {
    background-color: #5cb85c;
  }

  button:active {
    background-color: #d9d9d9;
  }
</style>

  