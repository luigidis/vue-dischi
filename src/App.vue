<template>
  <div id="app">
    <MainHeader @select="onSelect" />
    <MainContent :selected="optionSel" />
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
