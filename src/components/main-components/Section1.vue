<template>
<section>
   <div class="container">
      <div class="row row-cols-2 row-cols-md-3 row-cols-lg-6 g-5">
         <img :class="{'bright':darkMode}" v-for="img in section1_data" :key="img.id" :src="require('../../assets/img/brands/' + img.imgFileName)" :alt="img.alt">
      </div>
   </div>
</section>
</template>

<script>
import data from '../siteContent.json'

export default {
   name: 'Section1',
   data(){
      return {
         section1_data: [],
         img: null
      }
   },
   props: {
      darkMode: Boolean
   },
   methods: {
      getData(){
         this.section1_data = data.section_1
      }
   },
   created(){
      this.getData()
   }
}
</script>

<style lang="scss" scoped>
section {
   min-height: 8rem;
   background-color: var(--header-bg);
   border-top: 1px #E9ECEF solid;

   img {
      height: 1.5rem;
   }

   .bright {
      filter: brightness(1.5);
   }
}

</style>
