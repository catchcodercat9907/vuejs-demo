<template>
  <div id="app">
    <Header />
    <Todoes />
  </div>
</template>

<script>
import Header from './components/Header'
import Todoes from './components/Todoes'

export default {
  name: 'App',
  components: { Header, Todoes }
}
</script>

<style>
#app {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
    Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
</style>
