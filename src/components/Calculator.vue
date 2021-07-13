<template>
  <div>
    <h1> Hello World! </h1>
    <h3> This is new era of Calculator </h3>
  </div>

  <div class="calculator">
    <div class="display"> Hey new Calculator </div>
    <div>Hey </div>
    <div>Hey </div>
    <div>Hey </div>
    <div>Hey </div>
    <div>v</div>
    <div>Hey </div>
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
  grid-column: 1 / 5;
  background-color: blue;
  color: white; 
}

</style>
