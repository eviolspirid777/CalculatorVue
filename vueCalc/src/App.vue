<template>
<div class="calculator">
  <div class="calculator__output">{{textbox}}</div>
  <div class="calculator__keys">
    <button @click="plusClick">+</button>
    <button @click="minusClick">-</button>
    <button @click="multClick">*</button>
    <button @click="divClick">/</button>
    <button @click="nineClick">9</button>
    <button @click="eightClick">8</button>
    <button @click="sevenClick">7</button>
    <button @click="delClick">del</button>
    <button @click="sixClick">6</button>
    <button @click="fiveClick">5</button>
    <button @click="fourClick">4</button>
    <button @click="factClick">!n</button>
    <button @click="threeClick">3</button>
    <button @click="twoClick">2</button>
    <button @click="oneClick">1</button>
    <button @click="equalClick">=</button>
    <button @click="dotClick">,</button>
    <button @click="nulClick">0</button>
    <button @click="expClick">exp</button>
    <button @click="exponentiationClick">x^y</button>
    <button @click="cosClick">cos</button>
    <button @click="sinClick">sin</button>
    <button @click="tgClick">tg</button>
    <button @click="arctgClick">arctg</button>
    <button @click="m1PlusClick">M1+</button>
    <button @click="m1MinusClick">M1-</button>
    <button @click="m1RClick">M1R</button>
    <button @click="m1CClick">M1C</button>
    <button @click="m2PlusClick">M2+</button>
    <button @click="m2MinusClick">M2-</button>
    <button @click="m2RClick">M2R</button>
    <button @click="m2CClick">M2C</button>
    <button @click="lnClick">Ln</button>
    <button @click="logClick">Log</button>
  </div>
</div>
</template>

<script>
  import { ref } from 'vue'

  export default{
    setup(){
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
    if(text[1] == '^')
        result = Math.pow(oper1, oper2)
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
    M1.value = 0
  }
  const m2CClick = () =>{
    M2.value = 0
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
  const factClick = () => {
    var result = 1
    for(var i = 1; i <= parseFloat(textbox.value);i++){
      result *= i
    }
    textbox.value = result
  }
  const dotClick = () =>{
    textbox.value += `.`
  }
  const expClick = () =>{
    textbox.value =  Math.exp(textbox.value)
  }
  const exponentiationClick = () => textbox.value += " ^ "
  const cosClick = () => {
    textbox.value = Math.cos(textbox.value);
  }
  const sinClick = () => {
    textbox.value = Math.sin(textbox.value);
  }
  const tgClick = () => {
    textbox.value = Math.tan(textbox.value);
  }
  const arctgClick = () => {
    textbox.value = Math.atan(textbox.value);
  }
  const lnClick = () => {
    textbox.value = Math.log(textbox.value)
  }
  const logClick = () => {
                                                        //напиши обработку этого события
    }
  return{
    textbox,
    M1,
    M2,
    nulClick,
    oneClick,
    twoClick,
    threeClick,
    fourClick,
    fiveClick,
    sixClick,
    sevenClick,
    eightClick,
    nineClick,
    delClick,
    equalClick,
    plusClick,
    minusClick,
    divClick,
    multClick,
    m1RClick,
    m2RClick,
    m1CClick,
    m2CClick,
    m1PlusClick,
    m2PlusClick,
    m1MinusClick,
    m2MinusClick,
    factClick,
    dotClick,
    expClick,
    exponentiationClick,
    cosClick,
    sinClick,
    tgClick,
    arctgClick,
    lnClick,
    logClick
  }
}
}
</script>



<style scoped>

</style>
