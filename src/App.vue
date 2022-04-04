<template>
  <div id="app">
    <header-site :darkMode="darkMode"/>
    <settings-site @setDarkMode="setDarkMode"/>
    <main-site />
    <footer-site />
  </div>
</template>

<script>
import HeaderSite from './components/HeaderSite.vue'
import SettingsSite from './components/SettingsSite.vue'
import MainSite from './components/MainSite.vue'
import FooterSite from './components/FooterSite.vue'

export default {
  name: 'App',
  components: {
    HeaderSite,
    SettingsSite,
    MainSite,
    FooterSite
  },
  data(){
    return {
      darkMode: false
    }
  },
  methods: {
    setDarkMode(value){
      this.darkMode = value
    }
  }
}
</script>

<style lang="scss">
@import '~bootstrap';
@import './assets/scss/global.scss';
</style>
