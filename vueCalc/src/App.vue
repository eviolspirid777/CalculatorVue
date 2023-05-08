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
export default{
    data(){
      textbox = '',
      M1 = 0,
      M2 = 0
  },
    methods:{
      nulClick(){
        textbox.value +='0'
      },
      oneClick(){
        textbox.value += '1'
      },
      twoClick() {
        textbox.value += '2'
      },
      threeClick(){
        textbox.value +='3'
      },
      fourClick (){
        textbox.value +='4'
      },
      fiveClick(){
        textbox.value +='5'
      },
      sixClick(){
        textbox.value +='6'
      },
      sevenClick(){
        textbox.value +='7'
      },
      eightClick(){
        textbox.value +='8'
      },
      nineClick(){
        textbox.value +='9'
      },
      delClick(){
        textbox.value =''
      },
      equalClick(){
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
      },
      plusClick(){
        textbox.value += ' + '
      },
      minusClick(){
        textbox.value += ' - '
      },
      divClick(){
        textbox.value += ' / '
      },
      multClick(){
        textbox.value += ' * '
      },
      m1RClick(){
        textbox.value += M1.value
      },
      m2RClick(){
        textbox.value += M2.value
      },
      m1CClick(){
        M1.value = 0
      },
      m2CClic(){
        M2.value = 0
      },
      m1PlusClick(){
        M1.value = parseFloat(M1.value) + parseFloat(textbox.value)
      },
      m2PlusClick(){
        M1.value = parseFloat(M1.value) + parseFloat(textbox.value)
      },
      m1MinusClick(){
        M1.value = parseFloat(M1.value) - parseFloat(textbox.value)
      },
      m2MinusClick(){
        M1.value = parseFloat(M2.value) - parseFloat(textbox.value)
      },
      factClick(){
        var result = 1
        for(var i = 1; i <= parseFloat(textbox.value);i++){
          result *= i
        }
        textbox.value = result
      },
      dotClick(){
        textbox.value += `.`
      },
      expClick(){
        textbox.value =  Math.exp(textbox.value)
      },
      exponentiationClick() {
        textbox.value += " ^ "
      },
      cosClick () {
        textbox.value = Math.cos(textbox.value);
      },
      sinClick () {
        textbox.value = Math.sin(textbox.value);
      },
      tgClick () {
        textbox.value = Math.tan(textbox.value);
      },
      arctgClick () {
        textbox.value = Math.atan(textbox.value);
      },
      lnClick (){
        textbox.value = Math.log(textbox.value)
      },
      logClick () {
                                                            //напиши обработку этого события
      }
  }
}
</script>



<style scoped>

</style>
