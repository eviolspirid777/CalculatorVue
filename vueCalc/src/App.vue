<template>
  <div class="calculator">
    <div class="calculator__output">{{textbox}}</div>
    <div class="calculator__keys">
      <button @click="m1PlusClick" class="calculator__key calculator__key--memory">M1+</button>
      <button @click="m1MinusClick" class="calculator__key calculator__key--memory">M1-</button>
      <button @click="m1RClick" class="calculator__key calculator__key--memory">M1R</button>
      <button @click="m1CClick" class="calculator__key calculator__key--memory">M1C</button>
      <button @click="m2PlusClick" class="calculator__key calculator__key--memory">M2+</button>
      <button @click="m2MinusClick" class="calculator__key calculator__key--memory">M2-</button>
      <button @click="m2RClick" class="calculator__key calculator__key--memory">M2R</button>
      <button @click="m2CClick" class="calculator__key calculator__key--memory">M2C</button>
      <button @click="plusClick" class="calculator__key calculator__key--operator">+</button>
      <button @click="minusClick" class="calculator__key calculator__key--operator">-</button>
      <button @click="multClick" class="calculator__key calculator__key--operator">*</button>
      <button @click="divClick" class="calculator__key calculator__key--operator">/</button>
      <button @click="nineClick" class="calculator__key">9</button>
      <button @click="eightClick" class="calculator__key">8</button>
      <button @click="sevenClick" class="calculator__key">7</button>
      <button @click="delClick" class="calculator__key calculator__key--operator">&larr;</button>
      <button @click="sixClick" class="calculator__key">6</button>
      <button @click="fiveClick" class="calculator__key">5</button>
      <button @click="fourClick" class="calculator__key">4</button>
      <button @click="clearClick" class="calculator__key calculator__key--operator">C</button>
      <button @click="threeClick" class="calculator__key">3</button>
      <button @click="twoClick" class="calculator__key">2</button>
      <button @click="oneClick" class="calculator__key">1</button>
      <button @click="sqrtClick" class="calculator__key calculator__key--operator">√x</button>
      <button @click="dotClick" class="calculator__key calculator__key--operator">,</button>
      <button @click="nulClick" class="calculator__key">0</button>
      <button @click="exponentiationClick" class="calculator__key calculator__key--operator">x^y</button>
      <button @click="equalClick" class="calculator__key calculator__key--enter">=</button>
      <button @click="cosClick" class="calculator__key calculator__key--operator">cos</button>
      <button @click="sinClick" class="calculator__key calculator__key--operator">sin</button>
      <button @click="tgClick" class="calculator__key calculator__key--operator">tg</button>
      <button @click="arctgClick" class="calculator__key calculator__key--operator">arctg</button>
      <button @click="lnClick" class="calculator__key calculator__key--operator">Ln</button>
      <button @click="expClick" class="calculator__key calculator__key--operator">exp</button>
      <button @click="factClick" class="calculator__key calculator__key--operator">!n</button>
      <button @click="reverseClick" class="calculator__key calculator__key--operator">1/X</button>
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
    checkSign(){
      if(this.textbox.includes('+') || this.textbox.includes('-') ||this.textbox.includes('*') || this.textbox.includes('/'))
      {
        return true;
      }
      else
      {
        return false;
      }
    },
    nulClick() {
      if(!this.textbox.startsWith('0'))
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
        this.textbox = result;
      },
      plusClick(){
        if(!this.checkSign())
          this.textbox += ' + '
      },
      minusClick(){
        if(!this.checkSign())
          this.textbox += ' - '
      },
      divClick(){
        if(!this.checkSign())
          this.textbox += ' / '
      },
      multClick(){
        if(!this.checkSign())
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
      m2CClick(){
        this.M2 = 0
      },
      m1PlusClick(){
        this.M1 = parseFloat(this.M1) + parseFloat(this.textbox)
      },
      m2PlusClick(){
        this.M2 = parseFloat(this.M1) + parseFloat(this.textbox)
      },
      m1MinusClick(){
        this.M1 = parseFloat(this.M1) - parseFloat(this.textbox)
      },
      m2MinusClick(){
        this.M2 = parseFloat(this.M2) - parseFloat(this.textbox)
      },
      factClick(){
        if(!this.textbox.includes('.'))
        {
          var result = 1
          for(var i = 1; i <=parseFloat(this.textbox);i++){
          result *= i
          }
          this.textbox = result
        }
        else
          this.textbox = "0";
      },
      reverseClick(){
        this.textbox = 1 / parseFloat(this.textbox)
      },
      dotClick(){
      this.textbox += `.`
      },
      expClick(){
      this.textbox = Math.exp(this.textbox)
      },
      exponentiationClick() {
      this.textbox += " ^ "
      },
      cosClick(){
      this.textbox = Math.cos(this.textbox);
      },
      sinClick(){
      this.textbox = Math.sin(this.textbox);
      },
      tgClick(){
      this.textbox = Math.tan(this.textbox);
      },
      arctgClick(){
      this.textbox = Math.atan(this.textbox);
      },
      lnClick(){
      this.textbox = Math.log(this.textbox);
      },
      sqrtClick(){
        this.textbox = Math.sqrt(parseFloat(this.textbox));
      }
  }
}
</script>

<style>
.calculator {
  border-radius: 20px;
  box-shadow: 0px 3px 6px 0px rgba(126, 7, 7, 0.788), 0px 2px 4px 0px rgba(0, 0, 0, 0.12);
  margin-inline-start: auto;
  margin-inline-end: auto;
  margin-block-start: 32px;
  max-inline-size: 1000px;
  overflow: hidden;
}
.calculator__output {
  height: 40px;
  width: 989px;
  background: rgba(126, 7, 7, 0.685);
  color: hsl(0, 0%, 100%);
  font-size: 32px;
  padding-block-start: 8px;
  padding-block-end: 8px;
  padding-inline-end: 12px;
  text-align: end;
}
.calculator__keys {
  display: grid;
  grid-template-columns: repeat(4,1fr);
  grid-gap: 1px;
  background: hsl(0, 56%, 27%);
}
.calculator__key {
  border-radius: 5px; 
  background: hsla(207, 25%, 86%, 0.788);
  border: none;
  padding-block-start: 25px;
  padding-block-end: 16px;
  padding-inline-end: 19px;
  padding-inline-start: 20px;
  font-size: 20px;
  transition: background 0.6s;
}
.calculator__key:hover {
  background: hsla(207, 25%, 86%, 0.349);

}
.calculator__key:active,
.calculator__key:focus {
  box-shadow: 0 0 8px 0 rgba(0, 0, 0, 0.3) inset;
  outline: none;
}
.calculator__key--operator {
  background: hsl(0, 25%, 86%);
}
.calculator__key--memory{
  background: hsla(207, 25%, 86%, 0.623);
}
.calculator__key--operator:active {
  background: hsl(208, 24%, 80%);
}

.calculator__key--enter{
  background: hsla(207, 24%, 80%, 0.281);
}

.calculator__key--enter:hover {
  background: hsla(0, 100%, 50%, 0.527);
  cursor: pointer;
}
</style>