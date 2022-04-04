<template>
  <div id="app">
    <header-site :darkMode="darkMode"/>
    <settings-site @setDarkMode="setDarkMode"/>
    <main-site :darkMode="darkMode" />
    <footer-site />
    <button @click="toTop()" class="to-top position-fixed d-flex align-items-center justify-content-center"><i class="fa-solid fa-arrow-up"></i></button>
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
    },
    toTop(){
      window.scrollTo(0, 0)
    }
  }
}
</script>

<style lang="scss">
@import '~bootstrap';
@import './assets/scss/global.scss';

.to-top {
  width: 2.5rem;
  height: 2.5rem;
  bottom: 1rem;
  right: 1rem;
  color: var(--white);
  border: 0;
  border-radius: 50%;
  background-color: var(--primary);
  box-shadow: 0 0 4px 0 var(--shadows);
  z-index: 20;
}
</style>
