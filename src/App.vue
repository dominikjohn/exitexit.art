<template>
  <div id="app">
    <img src="./assets/exit_logo2_transparent.png" width="150"/>
    <div class="max-width">
      <div v-if="!showImpressum && !showMore">
        <ChatContainer id="chatcontainer" ref="chatcontainer" class="chat"/>
      </div>
      <div v-if="showImpressum && !showMore">
        <a href="#" @click="backFunction">&laquo; Zurück</a>
        <Impressum />
      </div>
      <div v-if="showMore && !showImpressum">
        <a href="#" @click="backFunction">&laquo; Zurück</a><br /><br /><br />
        <p>Gefördert vom Fonds Darstellende Künste aus Mitteln der Beauftragten der Bundesregierung für Kultur und Medien im Rahmen von NEUSTART KULTUR.</p>
        <img src="./assets/fond.png" width="50%" />
      </div>
    </div>
    <br/>
    <p><a href="#" @click="showMoreFunction">Mehr Infos</a> | <a href="#" @click="showImpressumFunction">Impressum</a></p>
  </div>
</template>

<script>
import ChatContainer from './components/ChatContainer.vue'
import Impressum from './components/Impressum'

export default {
  data() {
    return {
      showMore: false,
      showImpressum: false
    }
  },
  name: 'App',
  components: {
    ChatContainer,
    Impressum
  },
  methods: {
    showImpressumFunction() {
      this.showMore = false
      this.showImpressum = true
    },
    showMoreFunction() {
      this.showMore = true
      this.showImpressum = false
    },
    backFunction() {
      this.showMore = false
      this.showImpressum = false
    }
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

a {
  color: #000 !important;

}

.max-width {
  margin-top: 30px;
  background-image: url('assets/exit_bg2_grüngelb-03-03.png');
  color: #000;
  max-width: 550px;
  height: 550px;
  padding: 35px;
  overflow-y: scroll;
  margin-left: auto;
  margin-right: auto;
}
</style>
