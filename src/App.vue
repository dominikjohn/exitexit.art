<template>
  <div id="app">
    <a href="#"><img src="./assets/exit_logo2_transparent.png" width="120" @click="backFunction"/></a><br/><br/>
    <div class="max-width">
      <div v-if="!showImpressum && !showMore">
        <ChatContainer id="chatcontainer" ref="chatcontainer" class="chat"/>
      </div>
      <div v-if="showImpressum && !showMore">
        <a href="#" @click="backFunction" class="backbutton">&laquo; Zurück</a><br/><br/>
        <Impressum/>
        <br/>
        <a href="#" @click="backFunction" class="backbutton">&laquo; Zurück</a><br/>
      </div>
      <div v-if="showMore && !showImpressum">
        <a href="#" @click="backFunction" class="backbutton">&laquo; Zurück</a><br/><br/>
        <div style="background-color: #fff; text-align: left; padding: 15px;">

          <iframe src="https://player.vimeo.com/video/671639688?h=4425c86e25" style="width: 100%; height: 300px;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
          <p><a href="https://vimeo.com/671639688">EXIT Performance Installation 2021</a> from <a href="https://vimeo.com/karoserafin">Karolina Serafin</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
          <p>
            <i>Im Exit liegt das Aus- und das Einsteigen. Im Exit
              tauchen Gedanken und Geschichten noch einmal kurz auf,
              bevor sie losgelassen werden. Im Exit kann man nichts festhalten. Im Exit passiert Transformation. Im Exit
              findet man den luftleeren Raum. Das klingt romantisch. Im Exit wird fragmentiert, neu geordnet und
              sortiert.
              Im Exit liegt die Hoffnung auf paradiesische, neue Zustände. Das kann’s doch nicht gewesen sein.</i></p>

          <p>Die drei Künstlerinnen - Isabella Sedlak (Regisseurin und Autorin), Karolina Serafin (Videokünstlerin) und
            Hanna Lenz (Szenografin) - erarbeiten interdisziplinär über mehrere Wochen ein Baukastensystem für Text und
            Sprache. Ein sich ständig wandelndes “Ich” begibt sich auf eine Reise durch alltägliche und fantastische
            Welten, wechselt schamlos zwischen der Analyse von Arbeitsbedingungen für freischaffende
            Theaterkünstler:innen
            und Komfortzonen-Abriss-Plänen. In ihrem Projekt “EXIT” erweitern die Künstlerinnen die Grenzen ihrer
            jeweiligen Disziplinen und entwickeln eine experimentelle und spielerische Praxis der künstlerischen
            Zusammenarbeit.</p>

          <p>Vom 26. bis 28. November 2021 kann das Publikum die performative Rauminstallation besuchen, in der die
            Künstlerinnen weiter sortieren, zerstückeln und neu organisieren. Einen ersten Einblick in die Arbeit gibt
            es
            auf www.exitexit.art und auf Instagram @exitexit.art</p>

          <p>Öffnungszeiten:<br/>
            26. Nov 16-21 Uhr<br/>
            27. Nov 14-21 Uhr<br/>
            28. Nov 14-19 Uhr<br/>
          </p>
          <p>
            @ PremArts, Oppelner Str. 34, 10997 Berlin</p>
          <p>

            Konzept, Performance, Installation Isabella Sedlak, Karolina Serafin, Hanna Lenz<br/><br/>

            Produktionsleitung Florian Meyer<br/><br/>

            Webgestaltung Dominik John / <a target="_blank" href="www.polyidea.de"><u>polyidea</u></a><br/><br/>

            Social Media / PR Felicitas Wetzel<br/><br/>

            Dokumentation Regina Teichs<br/><br/>

            Auf Grund der aktuellen Corona Lage gilt auch bei dieser Veranstaltung die 2G Regel.
            Zusätzlich möchten wir Besucher:innen bitten, Masken zu tragen.
            Die Künstler:innen werden täglich getestet.</p>
          <small><p>
            The three artists - Isabella Sedlak (director and author), Karolina Serafin (video artist) and Hanna Lenz
            (scenographer) - create an interdisciplinary modular system for text and language over several weeks. A
            constantly changing "I" embarks on a journey through everyday and fantastic worlds, shamelessly alternating
            between the analysis of working conditions for freelance theater artists and comfort-zone-demolition-plans.
            In their project "EXIT" the artists expand the boundaries of their respective disciplines and develop an
            experimental and playful practice of artistic collaboration.</p>

            <p>On November 26.-28. 2021, the public can visit the performance installation in which the artists continue
              to
              sort, dismantle, and reorganize. For a sneak peek of the work, visit exitexit.art or Instagram
              @exitexit.art</p>

            <p>Opening hours and place: see above</p>

            <p>Due to the current Corona situation, the 2G rule also applies at this event.
              Additionally we would like to ask visitors to wear masks. The artists will be tested daily.

            </p></small>
          <p>Gef&ouml;rdert vom Fonds Darstellende Künste aus Mitteln der Beauftragten der Bundesregierung für Kultur
            und
            Medien im Rahmen von NEUSTART KULTUR.</p>
          <img src="./assets/fond.png" width="50%"/>
        </div>
        <br/>
        <a href="#" @click="backFunction" class="backbutton">&laquo; Zurück</a><br/><br/>
      </div>
    </div>
    <br/>
    <p><a href="#" @click="showMoreFunction"><u>Mehr Infos</u></a> <br/><small><a href="#"
                                                                                  @click="showImpressumFunction">Impressum</a></small>
    </p>
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
  },
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
  background-image: url('assets/exit_bg5-03.png');
  background-size: 100% 100%;
  color: #000;
  max-width: 550px;
  height: 700px;
  padding: 15px;
  overflow-y: scroll;
  margin-left: auto;
  margin-right: auto;
}

.backbutton {
  background-color: #00FFBC;
  text-align: center;
  padding: 5px 15px 5px 15px;
  border-radius: 15px 15px 15px 0px;
}
</style>
