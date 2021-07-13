<template>
  <div>
    <h1 class="text"> Hello World! </h1>
    <h3> This is new era of Calculator </h3>
  </div>

  <div class="calculator">
    <div class="display"> <div class="number"> {{ current || '0' }} </div> </div>
    <div @click="clear" class="btn">AC</div>
    <div @click="sign" class="btn">+/-</div>
    <div @click="percent" class="btn">%</div>
    <div @click="divide" class="btn operator">÷</div>
    <div @click="append('7')" class="btn">7</div>
    <div @click="append('8')" class="btn">8</div>
    <div @click="append('9')" class="btn">9</div>
    <div @click="times" class="btn operator">x</div>
    <div @click="append('4')" class="btn">4</div>
    <div @click="append('5')" class="btn">5</div>
    <div @click="append('6')" class="btn">6</div>
    <div @click="minus" class="btn operator">-</div>
    <div @click="append('1')" class="btn">1</div>
    <div @click="append('2')" class="btn">2</div>
    <div @click="append('3')" class="btn">3</div>
    <div @click="add" class="btn operator">+</div>
    <div @click="append('0')" class=" btn zero">0</div>
    <div @click="dot" class="btn">.</div>
    <div @click="equal" class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      previous: null,
      current: '',
      operator: null,
      operatorClicked: false,
    }
  },
  methods: {
    clear() {
      this.current = '';
    },
    sign() {
      this.current = this.current.charAt(0) === '-' ? this.current.slice(1) : `- ${this.current}`;
    },
    percent() {
      this.current = `${parseFloat(this.current) / 100}`;
    },
    append(number) {
      if (this.operatorClicked) {
        this.current = '';
        this.operatorClicked = false;
      }
      this.current = `${this.current}${number}`;
    },
    dot() {
      if (this.current.indexOf('.') === -1) {
        this.append('.');
      }
    },
    setPrevious() {
      this.previous = this.current;
      this.operatorClicked = true;
    },
    divide() {
      this.operator = (a,b) => a / b;
      this.setPrevious();
    },
    times() {
      this.operator = (a,b) => a * b;
      this.setPrevious();
    },
    minus() {
      this.operator = (a,b) => b - a;
      this.setPrevious();
    },
    add() {
      this.operator = (a,b) => a + b;
      this.setPrevious();
    },
    equal() {
      this.current = `${this.operator(parseFloat(this.current), parseFloat(this.previous))}`;
      this.previous = null;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.calculator {
  width: 500px;
  margin: 0 auto;
  display: grid; 
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto); 
  align-items: center;
 
}

.display {
  font-size: 40px;
  grid-column: 1 / 5;
  /* background: #f9d72f; */
  background: linear-gradient( #f9d72f, #e0a82e);
  /* #e0a82e */
  color: rgb(235, 215, 215); 
  /* border-radius: 35% 35%; */ 
  border-radius: 30px;
}

.number {
  width: 55%;
  margin: 30px auto;
  padding: 10px;
  background: #000000;
  align-content: center;
  text-align: center;
  border-radius: 20px;
}

.zero {
  grid-column: 1 / 3;
}

.btn {
  background-color: #eee;
  border: 1px solid #999;
  border-radius: 10px;
}

.operator {
  background-color: rgb(71, 194, 173);
  color: rgb(0, 17, 252);
}

.text {
  color: white;
  text-shadow: 2px 2px 4px #000000;
}

</style>
