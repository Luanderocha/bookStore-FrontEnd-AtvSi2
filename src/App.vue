<template>
  <div id="app">
    <Header/>
    <div id="itens">
      <Box/>
    </div>
  </div>
</template>

<script>

import Header from './components/Header'
import Box from './components/Box'

export default {
  name: 'App',
  components: {
  Header,
  Box
  },
}
</script>

<style>
  #app{
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
  #itens{
     margin : 2rem;
  }
</style>

