<template>
  <div class="result">
    <p>Reaction Time: {{score}} ms</p>
  </div>
</template>

<script>
export default {
   name: 'ResultComp',
   props: ['score']
}
</script>

<style>
  .result {
    width: 300px;
    padding: 10px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(18, 171, 127); 
    margin: 50px auto;
  }

  .result p {
    font-size: 18px;
    font-style: italic;
    font-family: monospace;
    color: white;
  }
</style>