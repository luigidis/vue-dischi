<template>
  <div id="app">
    <MainHeader @select="onSelect" @selectArtist="onArtist"/>
    <MainContent :selected="optionSel" :selectedArtist="selectedArtist" />
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue';
import MainContent from './components/MainContent.vue'

export default {
  name: 'App',
  data() {
    return {
      optionSel: '',
      selectedArtist: '',
    }
  },
  components: {
    MainHeader,
    MainContent,
  },
  methods: {
    onSelect(genre) {
      console.log('Passo l\' info', genre)
      this.optionSel = genre
    }
  },
    onArtist(artist) {
      console.log('Passo l\' info', artist)
      this.selectedArtist = artist
    }
}

</script>

<style lang="scss">
@import './styles/variables.scss';

html {
  body {
    background-color: $main-bg-color;
  }
}
</style>
