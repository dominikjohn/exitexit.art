<template>
  <div id="app">
    <h1>exitexit.art</h1>
    <div class="max-width">
      <ChatContainer/>
    </div>
  </div>
</template>

<script>
import ChatContainer from './components/ChatContainer.vue'

export default {
  name: 'App',
  components: {
    ChatContainer
  }
}
</script>

<style>
html, body, #app {
  background-color: #380538;
  color: #fff;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
.max-width {
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}
</style>
