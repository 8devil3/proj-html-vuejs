<template>
  <footer>
     <div class="container row justify-between">
        <div class="widget-1">
           <img src="../assets/img/logo-light.png" alt="Landrick logo">
           <p>Start working with Landrick that can provide everything you need to generate awarness, drive traffic, connect.</p>
           <div class="social-wrapper row">
              <div class="social-icons row justify-center align-center"><i class="fa-brands fa-facebook-f"></i></div>
              <div class="social-icons row justify-center align-center"><i class="fa-brands fa-instagram"></i></div>
              <div class="social-icons row justify-center align-center"><i class="fa-brands fa-twitter"></i></div>
              <div class="social-icons row justify-center align-center"><i class="fa-brands fa-linkedin"></i></div>
           </div>
        </div>
        <div class="widget-2 row justify-between">
         <div v-for="cat in links" :key="cat.id">
            <h3>{{ cat.category }}</h3>
            <nav>
               <ul>
                  <li v-for="link in cat.content" :key="link.id"><a href="#">{{ link.text }}</a></li>
               </ul>
            </nav>
         </div>
        </div>
        <div class="widget-3">
           <h3>Newsletter</h3>
           <p>Sign up and receive the latest tips via email.</p>
           <div class="newsletter-wrapper col">
               <label for="email">Write your email <span>*</span></label>
               <div class="input-wrapper">
                  <input type="email" id="email" placeholder="Your email:">
                  <i class="fa-regular fa-envelope"></i>
               </div>
            <button>subscribe</button>
           </div>

        </div>
     </div>
     <hr>
     <div class="colophon container row align-center justify-between">
        <p>&copy; 2020 Landrick. Design with <i class="fa-solid fa-heart"></i> by <a href="https://www.instagram.com/8devil_art/">8devil</a></p>
        <div class="row align-center">
           <img v-for="img in imgPayments" :key="img.id" :src="require('../assets/img/payments/' + img.fileName)" :alt="img.alt">
        </div>
     </div>
  </footer>
</template>

<script>
export default {
   name: 'FooterSite',
   data(){
      return {
         links: [
            {
               id: 1,
               category: 'company',
               content: [
                  {
                     id: 1,
                     url: '#',
                     text: 'About us',
                  },
                  {
                     id: 2,
                     url: '#',
                     text: 'Services',
                  },
                  {
                     id: 3,
                     url: '#',
                     text: 'Team',
                  },
                  {
                     id: 4,
                     url: '#',
                     text: 'Pricing',
                  },
                  {
                     id: 5,
                     url: '#',
                     text: 'Project',
                  },
                  {
                     id: 6,
                     url: '#',
                     text: 'Carrers',
                  },
                  {
                     id: 7,
                     url: '#',
                     text: 'Blog',
                  },
                  {
                     id: 8,
                     url: '#',
                     text: 'Login',
                  },
               ]
            },
            {
               id: 2,
               category: 'useful links',
               content: [
                  {
                     id: 9,
                     url: '#',
                     text: 'Terms of Services',
                  },
                  {
                     id: 10,
                     url: '#',
                     text: 'Privacy Policy',
                  },
                  {
                     id: 11,
                     url: '#',
                     text: 'Documentation',
                  },
                  {
                     id: 12,
                     url: '#',
                     text: 'Changelog',
                  },
                  {
                     id: 13,
                     url: '#',
                     text: 'Components',
                  }
               ]
            }
         ],
         imgPayments: [
            {
               id: 1,
               fileName: 'american-ex.png',
               alt: 'Amenrican Express'
            },
            {
               id: 2,
               fileName: 'discover.png',
               alt: 'Discover'
            },
            {
               id: 3,
               fileName: 'master-card.png',
               alt: 'Mastercard'
            },
            {
               id: 4,
               fileName: 'paypal.png',
               alt: 'PayPal'
            },
            {
               id: 5,
               fileName: 'visa.png',
               alt: 'Visa'
            }
         ]
      }
   }
}
</script>

<style lang="scss" scoped>
footer {
   background-color: var(--footer-bg);
   color: var(--footer-links-text);
   padding-top: 4rem;
   margin-top: 6rem;

   h3 {
      color: var(--footer-headings);
      font-weight: 400;
      margin-bottom: 1.5rem;
      text-transform: capitalize;
   }

   .container {
      .widget-1 {
         width: 30%;
   
         img {
            display: block;
            height: 1.5rem;
            margin-bottom: 1.5rem;
         }

         .social-wrapper {
            margin-top: 2rem;

            .social-icons {
               font-size: 1rem;
               height: 2rem;
               width: 2rem;
               margin-right: 0.25rem;
               border-radius: 0.25rem;
               border: 1px var(--icons-border) solid;
            }
         }
      }
   
      .widget-2 {
         flex-grow: 1;
         flex-shrink: 0;
         margin: 0 4rem;

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
               content: '\f054';
               font-family: 'Font Awesome 6 Free';
               font-weight: 900;
               font-size: 0.5rem;
               margin-right: 0.75rem;
               vertical-align: middle;
            }
         }
      }
   
      .widget-3 {
         width: 25%;
   
         .newsletter-wrapper{
            margin-top: 1rem;
   
            label{
               font-size: 0.8rem;
               font-weight: 700;
      
               span {
                  color: var(--input-label-mandatory);
               }
            }
   
            .input-wrapper {
               position: relative;
               margin: 0.25rem 0;
   
               input {
                  padding: 1rem 1rem 1rem 3.25rem;
                  border-radius: 0.25rem;
                  border: 0;
                  background-color: var(--input-bg);
                  width: 100%;
                  color: var(--footer-links-text);
   
                  &::placeholder, &:focus-within {
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
               background-color: var(--button-bg);
               color: var(--button-text);
               font-size: 0.9rem;
               font-weight: 700;
               box-shadow: var(--button-shadow);
               cursor: pointer;
            }
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
         color: var(--input-label-mandatory);
         font-size: 0.9rem;
      }

      img {
         height: 1.5rem;
         margin-left: 0.25rem;
      }
   }
}


</style>
