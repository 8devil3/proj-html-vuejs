<template>
<section>
   <div class="container row align-center justify-between">
      <div class="left">
         <h2>{{ section4_data.title }}</h2>
         <p>{{ section4_data.content }}</p>
         <ul>
            <li v-for="feat in section4_data.features" :key="feat.id">{{ feat.text }}</li>
         </ul>
         <button class="btn btn-primary">read more <i class="fa-solid fa-arrow-right"></i></button>
      </div>
      <div class="right">
         <img :src="require('../../assets/img/' + section4_data.imgRightFilename)" :alt="section4_data.imgRightAlt">
      </div>
   </div>
</section>
</template>

<script>
import data from '../siteContent.json'

export default {
   name: 'Section4',
   data(){
      return {
         section4_data: {}
      }
   },
   methods: {
      getData(){
         this.section4_data = data.section_4
      }
   },
   created(){
      this.getData()
   }
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
