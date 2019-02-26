<template>
  <div id="app">
    <b-container >
      <b-row>
        <b-col cols="4">
          <stock-card stockSymbol="MSFT"></stock-card>
        </b-col>
        <b-col cols="4">
          <stock-card stockSymbol="AAPL"></stock-card>
        </b-col>
      </b-row> 
    </b-container>
  </div>
</template>

<script>
import StockCard from './components/stocks/StockCard'
export default {
  name: 'app',
  components: {
    StockCard
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
