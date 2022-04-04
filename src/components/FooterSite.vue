<template>
   <footer>
      <div class="container">
         <div class="row row-cols-1 row-cols-lg-3 g-5">

            <!-- widget 1 -->
            <div class="widget-1 col">
               <img :src="require('../assets/img/' + footerData.widget_1.logo.fileName)" :alt="footerData.widget_1.logo.alt"/>
               <p>{{ footerData.widget_1.content }}</p>
               <div class="social-wrapper d-flex align-items-center">
                  <a :href="icon.url" v-for="icon in footerData.widget_1.social" :key="icon.id" class="social-icons d-flex justify-content-center align-items-center me-2">
                  <i :class="icon.fontAwesomeClasses"></i>
                  </a>
               </div>
            </div>
            <!-- / -->

            <!-- widget 2 -->
            <div class="widget-2 col">
               <div class="d-flex">
                  <div v-for="cat in footerData.widget_2.links" :key="cat.id" class="flex-shrink-0 me-5">
                     <h3>{{ cat.title }}</h3>
                     <nav>
                     <ul>
                        <li v-for="link in cat.content" :key="link.id">
                           <a href="#">{{ link.text }}</a>
                        </li>
                     </ul>
                     </nav>
                  </div>
               </div>
            </div>
            <!-- / -->
            
            <!-- widget 3 -->
            <div class="widget-3 col">
               <h3>{{ footerData.widget_3.title }}</h3>
               <p>{{ footerData.widget_3.content }}</p>
               <div class="newsletter-wrapper">
                  <label for="email">{{ footerData.widget_3.inputLabel }} <span>*</span></label>
                  <div class="input-wrapper">
                     <input type="email" id="email" :placeholder="footerData.widget_3.inputPlaceholder"/>
                     <i class="fa-regular fa-envelope"></i>
                  </div>
                  <button class="btn w-100">{{ footerData.widget_3.btnSubmitTxt }}</button>
               </div>
            </div>
            <!-- / -->

         </div>
      </div>

      <hr />

      <!-- colophon -->
      <div class="colophon container d-flex justify-content-between align-items-center flex-wrap">
         <p class="m-0">&copy; {{ currYear }} Landrick. Design with <i class="fa-solid fa-heart"></i> by <a href="https://www.instagram.com/8devil_art/">8devil</a></p>
         <div class="d-flex">
            <img class="col" v-for="img in footerData.colophon.imgPayments" :key="img.id" :src="require('../assets/img/payments/' + img.fileName)" :alt="img.alt"/>
         </div>
      </div>
      <!-- / -->

   </footer>
</template>

<script>
import data from "./siteContent.json";

export default {
  name: "FooterSite",
  data() {
    return {
      footerData: {},
      currYear: "",
    };
  },
  methods: {
    getData() {
      this.footerData = data.footer;
    },
    getYear() {
      this.currYear = new Date().getFullYear();
    },
  },
  created() {
    this.getData();
    this.getYear();
  },
};
</script>

<style lang="scss" scoped>
footer {
   background-color: var(--footer-bg);
   color: var(--footer-links-text);
   padding-top: 4rem;
   margin-top: 6rem;

   h3 {
      color: var(--footer-headings);
      font-size: 1.2rem;
      font-weight: 400;
      margin-bottom: 1.5rem;
      text-transform: capitalize;
   }

   .widget-1 {
      img {
      display: block;
      height: 1.5rem;
      margin-bottom: 1.5rem;
      }

      p {
         max-width: 23rem;
      }

      .social-wrapper {
      margin-top: 2rem;

      .social-icons {
         color: var(--footer-links-text);
         font-size: 1rem;
         height: 2rem;
         width: 2rem;
         margin-right: 0.25rem;
         border-radius: 0.25rem;
         border: 1px var(--icon-border) solid;
         transition: border 0.2s, color 0.2s;

         &:hover {
            color: var(--footer-links-hover);
            border: 1px var(--footer-links-hover) solid;
         }
      }
      }
   }

   .widget-2 {
      > div {
      margin: 0 1rem;
      }

      a {
      display: block;
      color: var(--footer-links-text);
      padding-bottom: 1rem;
      transition: color 0.3s;

      &:hover {
         color: var(--footer-links-hover);
      }

      &::before {
         content: "\f054";
         font-family: "Font Awesome 6 Free";
         font-weight: 900;
         font-size: 0.5rem;
         margin-right: 0.75rem;
         vertical-align: middle;
      }
      }
   }

   .widget-3 {
      .newsletter-wrapper {
      margin-top: 1rem;

      label {
         font-size: 0.8rem;
         font-weight: 700;

         span {
            color: var(--red);
         }
      }

      .input-wrapper {
         position: relative;
         margin: 0.25rem 0;

         input {
            padding: 1rem 1rem 1rem 3.25rem;
            border-radius: 0.25rem;
            border: 0;
            background-color: var(--footer-input-bg);
            width: 100%;
            color: var(--footer-links-text);

            &::placeholder,
            &:focus-within {
            color: var(--footer-links-text);
            }
         }

         .fa-envelope {
            position: absolute;
            top: 50%;
            left: 1.25rem;
            transform: translate(0, -50%);
         }
      }

      button {
         margin-top: 0.75rem;
         padding: 0.75rem 1rem;
         background-color: var(--footer-button-bg);
         color: var(--footer-button-text);
         font-size: 0.9rem;
         font-weight: 700;
         box-shadow: var(--footer-button-shadow);
         cursor: pointer;
      }
      }
   }

   hr {
      border: 0;
      height: 1px;
      background-color: var(--colophon-border);
      margin-top: 2rem;
   }

   .colophon {
      height: 6rem;

      a {
         color: #f60;

         &:hover {
         color: #f84;
         }
      }

      .fa-heart {
         color: var(--red);
         font-size: 0.9rem;
      }

      img {
         height: 1.5rem;
         margin-left: 0.25rem;
      }
   }
}
</style>
