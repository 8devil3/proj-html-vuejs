<template>
<header>
<nav class="navbar navbar-expand-lg">
   <div class="container-xl">
      <!-- logo -->
      <a class="navbar-brand" :href="headerData.logo_dark.url">
         <img v-if="!darkMode" :src="require('../assets/img/' + headerData.logo_dark.fileName)" :alt="headerData.logo_dark.alt" class="logo">
         <img v-else :src="require('../assets/img/' + headerData.logo_light.fileName)" :alt="headerData.logo_dark.alt" class="logo">
      </a>
      <!-- / -->

      <!-- menu mobile -->
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
         <i class="fa-solid fa-bars"></i>
      </button>
      <!-- / -->

      <!-- menu desktop -->
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
         <ul class="navbar-nav mx-auto mb-2 mb-lg-0 text-uppercase fw-bold">

            <li v-for="link in headerData.links" :key="link.id" :class="{'dropdown':link.submenu}" class="nav-item mx-3">
               <a :href="link.url" :class="{'dropdown-toggle':link.submenu}" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false" class="nav-link">{{ link.text }}</a>

               <ul v-show="link.submenu" class="dropdown-menu" aria-labelledby="navbarDropdown">
                  <li v-for="sublink in link.subLinks" :key="sublink.id">
                     <a class="dropdown-item" :href="sublink.url">{{ sublink.text }}</a>
                  </li>
               </ul>
            </li>
         </ul>

         <div class="d-flex align-items-center">
            <input type="text" id="search" class="search-input">
            <button class="search-icon" @click="toggleSearch()"><i class="fa-solid fa-magnifying-glass"></i></button>
            <a class="header-icons" v-for="login in headerData.userLogin" :key="login.id" :href="login.url "><i :class="login.fontAwesomeClasses"></i></a>
         </div>

      </div>
   </div>
</nav>
</header>
</template>

<script>
import data from './siteContent.json'

export default {
   name: 'HeaderSite',
   data() {
      return {
         headerData: [],
         searchInput: null
      }
   },
   props: {
      darkMode: Boolean
   },
   methods: {
      getData(){
         this.headerData = data.header
      },
      toggleSearch(){
         this.searchInput.classList.toggle('search-active')
      }
   },
   created(){
      this.getData()
   },
   mounted(){
      this.searchInput = document.querySelector('#search')
   }
}
</script>

<style lang="scss" scoped>
@import '~bootstrap';

header {
   background-color: var(--header-bg);

   .logo {
      height: 1.5rem;
   }

   .nav-link {
      font-size: 0.9rem;
      color: var(--headings);
      transition: color 0.2s;

      &:hover, &.active, &:focus {
         color: var(--primary);
      }
   }

   .navbar-toggler {
      border-color: var(--headings);
      color: var(--headings);
      display: flex;
      align-items: center;
      justify-content: center;
   }

   .dropdown-menu {
      background-color: var(--submenu-bg);
   }

   .dropdown-item {
      font-size: 0.9rem;
      color: var(--submenu-link);
      background-color: var(--submenu-bg);
   
      &:hover {
         background-color: var(--primary);
         color: var(--submenu-link-hover);
      }
   }

   .dropdown-toggle::after {
      content: '\f078';
      font-family: 'Font Awesome 6 Free';
      font-weight: 900;
      font-size: 0.8rem;
      border: 0;
      margin: 0 0 0 0.5rem;
      vertical-align: baseline;
   }

   .search-icon {
      background: transparent;
      border: 0;
      padding: 0.5rem 1rem;
      color: var(--default-text);
      font-size: 1rem;
   }

   .search-input {
      width: 0;
      opacity: 0;
      transition: width 0.4s, opacity 0.5s ease-in-out;
   }

   .search-active {
      width: 10rem;
      opacity: 1;
   }

   .header-icons {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 2.25rem;
      width: 2.25rem;
      background-color: var(--icon-bg);
      border: 1px var(--icon-border) solid;
      border-radius: 0.5rem;
      font-size: 1.2rem;
      color: var(--primary);
      box-shadow: 0 2px 4px 1px var(--shadows);
      margin-left: 0.5rem;
      cursor: pointer;
      transition: background-color 0.2s, color 0.2s, border 0.2s;

      &:hover {
         background-color: var(--primary);
         border-color: var(--primary);
         color: var(--header-bg);
      }
   }
}
</style>
