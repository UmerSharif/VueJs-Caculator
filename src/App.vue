<template>
  <div id="app">
   <Calculator />
    <router-view/>
  </div>
</template>
<script>
    import Calculator from './components/Calculator'

    export default {
        name: 'App',
        components: {
            Calculator
        }

    }
</script>
<style lang="scss">
  body {
    //background: rgb(131,58,180);
    //background: linear-gradient(90deg, rgba(131,58,180,1) 0%, rgba(253,29,29,1) 50%, rgba(252,176,69,1) 100%);
    display: flex;
    justify-content: center;
    align-items: center;
    line-height: 1.4;
    font-family: 'Signika', sans-serif;
  }

  #app {
    width: 270px;
    background: white;
    padding: 20px;
    margin: 30px;
    border-radius: 4px;
    opacity: 0.95;
  }

</style>
