<template>
<section>
   <div class="container row align-center justify-between">
      <div class="left">
         <h2>Build tools and<br>extensive documentation</h2>
         <p>You can combine all the Landrick templates into a single one, you can take a component frome the Application theme and use it in the Website.</p>
         <ul>
            <li>Digital Marketing Solutions for Tomorrow</li>
            <li>Our Talented &#38; Experienced Marketing Agency</li>
            <li>Create your own skin to match your brand</li>
         </ul>
         <button class="btn btn-primary">read more <i class="fa-solid fa-arrow-right"></i></button>
      </div>
      <div class="right">
         <img src="../../assets/img/1.png" alt="Build tools and extensive documentation">
      </div>
   </div>
</section>
</template>

<script>
export default {
   name: 'Section4'
}
</script>

<style lang="scss" scoped>
section {
   .left {
      width: 50%;

      p {
         margin: 2rem 0 1.5rem 0
      }

      ul {
         margin-bottom: 2rem;

         li {
            margin: 0.25rem 0;
   
            &::before {
               content: '\f058';
               font-family: 'Font Awesome 6 Free';
               font-weight: 40;
               font-size: 1rem;
               color: var(--primary);
               margin-right: 0.5rem;
               vertical-align: middle;
            }
         }
      }

      button .fa-arrow-right {
         font-size: 0.8rem;
         margin-left: 0.25rem;
      }
   }

   .right {
      width: 40%;

      img {
         width: 100%;
         height: 100%;
         object-fit: contain;
      }
   }
}
</style>
