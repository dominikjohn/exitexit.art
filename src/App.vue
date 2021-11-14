<template>
  <div id="app">
    <img src="./assets/exit_logo_transparent.png" width="150" />
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

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 20px;
}
.max-width {
  margin-top: 30px;
  background-color: #380538;
  color: #fff;
  max-width: 550px;
  height: 550px;
  padding: 35px;
  overflow-y: scroll;
  margin-left: auto;
  margin-right: auto;
}
</style>
