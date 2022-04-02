<template>
<header>
   <div class="container row justify-between align-center">
      <img src="../assets/img/logo-dark.png" alt="Landrick logo">
      <nav>
         <ul class="row align-center">
            <li v-for="link in links" :key="link.id"><a :href="link.url" :class="{'has-submenu':link.submenu}">{{ link.text }}</a></li>
         </ul>
      </nav>
      <div class="row align-center">
         <div class="input-wrapper">
            <!-- <input type="text" id="search"> -->
            <i class="fa-solid fa-magnifying-glass"></i>
         </div>
         
         <div class="row align-center">
            <div class="header-icons row align-center justify-center"><i class="fa-brands fa-github"></i></div>
            <div class="header-icons row align-center justify-center"><i class="fa-brands fa-stack-overflow"></i></div>
            <div class="header-icons row align-center justify-center"><i class="fa-regular fa-user"></i></div>
         </div>
      </div>
   </div>
</header>
</template>

<script>
export default {
   name: 'HeaderSite',
   data() {
      return {
         links: [
            {
               id: 1,
               url: "#",
               text: "home",
               submenu: false
            },
            {
               id: 2,
               url: "#",
               text: "landing",
               submenu: true
            },
            {
               id: 3,
               url: "#",
               text: "pages",
               submenu: true
            },
            {
               id: 4,
               url: "#",
               text: "docs",
               submenu: true
            }
         ]
      }
   }
}
</script>

<style lang="scss" scoped>

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
      
      /*input {
         border: 0;
         padding: 0.5rem;
         margin-right: 0.5rem;
         width: 8rem;
      }*/

      .fa-magnifying-glass {
         position: absolute;
         right: 1rem;
         top: 50%;
         transform: translate(0, -50%);
         font-size: 1rem;
         color: var(--header-search-icon);
      }
   }

   .header-icons {
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

</style>
