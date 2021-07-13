<template>
  <div>
    <h1> Hello World! </h1>
    <h3> This is new era of Calculator </h3>
  </div>

  <div class="calculator">
    <div class="display"> Hey new Calculator </div>
    <div>AC</div>
    <div>+/-</div>
    <div>%</div>
    <div>÷</div>
    <div>7</div>
    <div>8</div>
    <div>9</div>
    <div>x</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
    <div>-</div>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>+</div>
    <div class="zero">0</div>
    <div>.</div>
    <div>=</div>
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
  background-color: blue;
  color: white; 
}

.zero {
  grid-column: 1 / 3;
}

</style>
