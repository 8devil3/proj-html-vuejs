<template>
  <div id="app">
    <header-site />
    <main-site />
    <footer-site />
  </div>
</template>

<script>
import HeaderSite from './components/HeaderSite.vue'
import MainSite from './components/MainSite.vue'
import FooterSite from './components/FooterSite.vue'

export default {
  name: 'App',
  components: {
    HeaderSite,
    MainSite,
    FooterSite
  }
}
</script>

<style lang="scss">
// @import './assets/scss/global.scss';
@import '~bootstrap';
@import './assets/scss/_colors.scss';

#app {  
  font-family: 'Nunito', sans-serif;
  font-size: 16px;
  color: $default-txt;

  section {
    padding: 3rem 0;
  }

  h1, h2, h3 {
    color: $dark-blue;
    font-weight: 700;
  }

  strong {
    color: $primary;
  }

  button {
    text-transform: capitalize;
  }

  .btn-primary {
    background-color: $primary;
    border-color: $primary;

    &:hover {
      background-color: $primary-hover;
      border-color: $primary-hover;
    }
  }

  .btn-outline-primary {
    border-color: $primary;

    &:hover {
      background-color: $primary-hover;
      border-color: $primary-hover;
    }
  }

  ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  a {
    text-decoration: none;
  }
}

</style>
