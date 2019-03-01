<template>
  <div id="app">
      <stock-card-manager></stock-card-manager>
  </div>
</template>

<script>
import StockCardManager from './components/stocks/StockCardManager'
export default {
  name: 'app',
  components: {
    StockCardManager
  }
}
</script>

<style>
 body {
  margin: 0;
  padding: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen",
    "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue",
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #282c34;
  color: #0d7ceb;
  min-height: 100vh;
  padding-top: 60px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

</style>
