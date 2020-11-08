<template>
  <Counter />
</template>

<script>
  import Counter from './components/Counter'

  export default {
    name: 'App',
    components: {
      Counter,
    }
  };
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    outline: 0;
    box-sizing: border-box;
  }

  body {
    height: 100vh;
    width: 100%;
  }

  #app {
    height: 100vh;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    color: #2c3e50;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    text-align: center;

    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
</style>
