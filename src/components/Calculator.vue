<template>
  <div>
    <h1> Hello World! </h1>
    <h3> This is new era of Calculator </h3>
  </div>

  <div class="calculator">
    <div class="display"> <div class="number"> random number </div> </div>
    <div class="btn">AC</div>
    <div class="btn">+/-</div>
    <div class="btn">%</div>
    <div class="btn">÷</div>
    <div class="btn">7</div>
    <div class="btn">8</div>
    <div class="btn">9</div>
    <div class="btn">x</div>
    <div class="btn">4</div>
    <div class="btn">5</div>
    <div class="btn">6</div>
    <div class="btn">-</div>
    <div class="btn">1</div>
    <div class="btn">2</div>
    <div class="btn">3</div>
    <div class="btn">+</div>
    <div class=" btn zero">0</div>
    <div class="btn">.</div>
    <div class="btn">=</div>
  </div>
</template>

<script>
export default {
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.calculator {
  display: grid; 
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto); 
}

.display {
  font-size: 40px;
  grid-column: 1 / 5;
  background: linear-gradient( #f9d72f, #e0a82e);
  /* #e0a82e */
  color: rgb(235, 215, 215); 
}

.number {
  width: 25%;
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
  border: 1px solid #333;
}

</style>
