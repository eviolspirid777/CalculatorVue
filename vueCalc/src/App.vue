<template>

<div class="calculator">
  <div class="calculator__output">{{textbox}}</div>
  <div class="calculator__keys">
    <button @click="plusClick">+</button>
    <button @click="minusClick">-</button>
    <button @click="multClick">*</button>
    <button @click="divClick">/</button>
    <button @click="delClick">del</button>
    <button @click="nineClick">9</button>
    <button @click="eightClick">8</button>
    <button @click="sevenClick">7</button>
    <button @click="sixClick">6</button>
    <button @click="fiveClick">5</button>
    <button @click="fourClick">4</button>
    <button @click="threeClick">3</button>
    <button @click="twoClick">2</button>
    <button @click="oneClick">1</button>
    <button @click="nulClick">0</button>
    <button @click="equalClick">=</button>
    <button @click="m1RClick">M1R</button>
    <button @click="m1CClick">M1C</button>
    <button @click="m1PlusClick">M1+</button>
    <button @click="m1MinusClick">M1-</button>
    <button @click="m2RClick">M2R</button>
    <button @click="m2CClick">M2C</button>
    <button @click="m2PlusClick">M2+</button>
    <button @click="m2MinusClick">M2-</button>
  </div>
</div>

</template>

<script setup>
  import { ref } from 'vue'
  const textbox = ref('')
  const M1 = ref(0)
  const M2 = ref(0)
  
  const nulClick = () =>{
    textbox.value +='0'
  }

  const oneClick = () => {
    textbox.value += '1'
  }

  const twoClick = () => {
    textbox.value += '2'
  }
  const threeClick = () =>{
    textbox.value +='3'
  }
  const fourClick = () =>{
    textbox.value +='4'
  }
  const fiveClick = () =>{
    textbox.value +='5'
  }
  const sixClick = () =>{
    textbox.value +='6'
  }
  const sevenClick = () =>{
    textbox.value +='7'
  }
  const eightClick = () =>{
    textbox.value +='8'
  }
  const nineClick = () =>{
    textbox.value +='9'
  }
  const delClick = () =>{
    textbox.value =''
  }
  const equalClick = () =>{
    var result = 0;
    var text = textbox.value.split(' ');
    var oper1 = parseFloat(text[0]);
    var oper2 = parseFloat(text[2]);
    if(text[1] == '+')
        result = oper1 + oper2;
    if(text[1] == '-')
        result = oper1 - oper2;
    if(text[1] == '/')
        result = oper1 / oper2;
    if(text[1] == '*')
        result = oper1 * oper2;
    textbox.value = result;
  }
  const plusClick = () =>{
    textbox.value += ' + '
  }
  const minusClick = () =>{
    textbox.value += ' - '
  }
  const divClick = () =>{
    textbox.value += ' / '
  }
  const multClick = () =>{
    textbox.value += ' * '
  }
  const m1RClick = () =>{
    textbox.value += M1.value
  }
  const m2RClick = () =>{
    textbox.value += M2.value
  }
  const m1CClick = () =>{
    M1 = 0
  }
  const m2CClick = () =>{
    M2 = 0
  }
  const m1PlusClick = () =>{
    M1.value = parseFloat(M1.value) + parseFloat(textbox.value)
  }
  const m2PlusClick = () =>{
    M1.value = parseFloat(M1.value) + parseFloat(textbox.value)
  }
  const m1MinusClick = () =>{
    M1.value = parseFloat(M1.value) - parseFloat(textbox.value)
  }
  const m2MinusClick = () =>{
    M1.value = parseFloat(M2.value) - parseFloat(textbox.value)
  }
</script>



<style scoped>

</style>
