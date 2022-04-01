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
         <div>
            <h3>Company</h3>
            <nav>
               <ul>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
               </ul>
            </nav>
         </div>
         <div>
            <h3>Useful links</h3>
            <nav>
               <ul>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
                  <li><a href="#">About us</a></li>
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
     <div class="colophon row align-center justify-between"></div>
  </footer>
</template>

<script>
export default {
   name: 'FooterSite'

}
</script>

<style lang="scss" scoped>
footer {
   background-color: var(--footer-bg);
   color: var(--footer-links-text);

   h3 {
      color: var(--footer-headings);
      font-weight: 400;
      margin-bottom: 1.5rem;
   }

   .container {
      padding: 4rem 0;

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
         margin: 0 4rem;

         a {
            display: block;
            color: var(--footer-links-text);
            padding-bottom: 1rem;

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
         width: 30%;
   
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

   .colophon {
      height: 6rem;
      border-top: 1px var(--colophon-border) solid;
   }
}


</style>
