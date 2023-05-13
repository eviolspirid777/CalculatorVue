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
      <button @click="delClick">&larr;</button>
      <button @click="sixClick">6</button>
      <button @click="fiveClick">5</button>
      <button @click="fourClick">4</button>
      <button @click="clearClick">C</button>
      <button @click="threeClick">3</button>
      <button @click="twoClick">2</button>
      <button @click="oneClick">1</button>
      <button class="calculator__key--enter" @click="equalClick">=</button>
      <button @click="dotClick">,</button>
      <button @click="nulClick">0</button>
      <button @click="spaceClick">|__|</button>
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
      <button @click="expClick">exp</button>
      <button @click="factClick">!n</button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      textbox: '',
      M1: 0,
      M2: 0,
    }
  },
  methods: {
    nulClick() {
      this.textbox += '0'
    },
    oneClick() {
      this.textbox += '1'
    },
    twoClick() {
      this.textbox += '2'
    },
    threeClick() {
      this.textbox += '3'
    },
    fourClick() {
      this.textbox += '4'
    },
    fiveClick() {
      this.textbox += '5'
    },
    sixClick() {
      this.textbox += '6'
    },
    sevenClick() {
      this.textbox += '7'
    },
    eightClick() {
      this.textbox += '8'
    },
    nineClick() {
      this.textbox += '9'
    },
    delClick() {
      this.textbox = this.textbox.slice(0, this.textbox.length - 1);
    },
    clearClick(){
      this.textbox = ''
    },
    equalClick(){
        var result = 0;
        var text = this.textbox.split(' ');
        var oper1 = parseFloat(text[0]);
        var oper2 = parseFloat(text[2]);
        if(text[1] === '+')
            result = oper1 + oper2;
        else if(text[1] === '-')
            result = oper1 - oper2;
        else if(text[1] === '/')
        {
            if(oper2 !== 0)
              result = oper1 / oper2;
            else
              result = "Error!";
        }
        else if(text[1] === '*')
            result = oper1 * oper2;
        else if(text[1] === '^')
            result = Math.pow(oper1, oper2)
        else if(text[0] ==='LOG'){
          var strs = this.textbox.split(' ');
          var number = parseFloat(strs[2]);
          var base = parseFloat(strs[1]);
          result = Math.log(number) / Math.log(base);
        }
        this.textbox = result;
      },
      plusClick(){
        this.textbox += ' + '
      },
      minusClick(){
        this.textbox += ' - '
      },
      divClick(){
        this.textbox += ' / '
      },
      multClick(){
        this.textbox += ' * '
      },
      m1RClick(){
        this.textbox += this.M1
      },
      m2RClick(){
        this.textbox += this.M2
      },
      m1CClick(){
        this.M1 = 0
      },
      m2CClic(){
        this.M2 = 0
      },
      m1PlusClick(){
        this.M1 = parseFloat(this.M1) + parseFloat(this.textbox)
      },
      m2PlusClick(){
        this.M1 = parseFloat(this.M1) + parseFloat(this.textbox)
      },
      m1MinusClick(){
        this.M1 = parseFloat(this.M1) - parseFloat(this.textbox)
      },
      m2MinusClick(){
        this.M1 = parseFloat(this.M2) - parseFloat(this.textbox)
      },
      factClick(){
        var result = 1
        for(var i = 1; i <= parseFloat(this.textbox);i++){
          result *= i
        }
        this.textbox = result
      },
      dotClick(){
        this.textbox += `.`
      },
      spaceClick(){
        this.textbox += ' '
      },
      expClick(){
        this.textbox =  Math.exp(this.textbox)
      },
      exponentiationClick() {
        this.textbox += " ^ "
      },
      cosClick () {
        this.textbox = Math.cos(this.textbox);
      },
      sinClick () {
        this.textbox = Math.sin(this.textbox);
      },
      tgClick () {
        this.textbox = Math.tan(this.textbox);
      },
      arctgClick () {
        this.textbox = Math.atan(this.textbox);
      },
      lnClick (){
        this.textbox = Math.log(this.textbox);
      },
      logClick () {
        this.textbox += "LOG "
      },
  }
}
</script>