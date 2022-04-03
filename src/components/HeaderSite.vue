<template>
<header>
<nav class="navbar navbar-expand-lg">
   <div class="container-xl">
      <!-- logo -->
      <a class="navbar-brand" :href="headerData.logo.url">
         <img :src="require('../assets/img/' + headerData.logo.fileName)" :alt="headerData.logo.alt" class="logo">
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

         <!-- campo ricerca -->
         <form class="d-flex">
            <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
            <button class="btn btn-outline-success" type="submit">Search</button>
         </form>
         <!-- / -->

         <div class="d-flex align-items-center">
            <div v-for="login in headerData.userLogin" :key="login.id" class="header-icons">
               <a :href="login.url"><i :class="login.fontAwesomeClasses"></i></a>
            </div>
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
         headerData: []
      }
   },
   methods: {
      getData(){
         this.headerData = data.header
      }
   },
   created(){
      this.getData()
   }
}
</script>

<style lang="scss" scoped>
@import '../assets/scss/_colors.scss';
@import '~bootstrap';

header {
   background-color: $header-bg;

   .logo {
      height: 1.5rem;
   }

   .nav-link {
      font-size: 0.9rem;
      color: $dark-blue;
      transition: color 0.2s;

      &:hover, &.active {
         color: $primary;
      }
   }

   .navbar-toggler {
      border-color: $dark-blue;
      color: $dark-blue;
      display: flex;
      align-items: center;
      justify-content: center;
   }

   .dropdown-item:hover {
      color: $header-bg;
      background-color: $primary;
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

   .header-icons a {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 2.25rem;
      width: 2.25rem;
      background-color: $icon-bg;
      border: 1px $icon-border solid;
      border-radius: 0.5rem;
      font-size: 1.2rem;
      color: $primary;
      box-shadow: 0 2px 4px 1px #C5D0F2;;
      margin-left: 0.5rem;
      cursor: pointer;
      transition: background-color 0.2s, color 0.2s, border 0.2s;

      &:hover {
         background-color: $primary;
         border-color: $primary;
         color: $header-bg;
      }
   }
}

/*
header {
   background-color: var(--header-bg);
   padding: 1rem;

   img {
      display: block;
      height: 1.5rem;
   }

   nav a {
      display: block;
      padding: 0.5rem 1rem;
      margin: 0 0.5rem;
      text-transform: uppercase;
      color: var(--header-links);
      font-size: 0.9rem;
      font-weight: 700;
      letter-spacing: 1px;

      &:hover {
         color: var(--header-links-hover);
      }
   }
      .has-submenu::after {
         content: '\f078';
         font-size: 0.8rem;
         font-family: 'Font Awesome 6 Free';
         font-weight: 900;
         margin-left: 0.5rem;
      }

   .input-wrapper {
      position: relative;
      
      .fa-magnifying-glass {
         position: absolute;
         right: 1rem;
         top: 50%;
         transform: translate(0, -50%);
         font-size: 1rem;
         color: var(--header-search-icon);
      }
   }

   .header-icons a {
      height: 2.25rem;
      width: 2.25rem;
      background-color: var(--header-icons-bg);
      border: 1px var(--header-icons-border) solid;
      border-radius: 0.5rem;
      font-size: 1.2rem;
      color: var(--header-icons-text);
      box-shadow: var(--header-icons-shadow);
      margin-left: 0.5rem;
      cursor: pointer;
      transition: background-color 0.2s, color 0.2s, border 0.2s;

      &:hover {
         background-color: var(--header-icons-bg-hover);
         border-color: var(--header-icons-border-hover);
         color: var(--header-icons-text-hover)
      }
   }


}
*/
</style>
