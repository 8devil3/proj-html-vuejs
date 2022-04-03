<template>
<section>
   <div class="container row justify-between align-center">
      <img v-for="img in section1_data" :key="img.id" :src="require('../../assets/img/brands/' + img.imgFileName)" :alt="img.alt">
   </div>
</section>
</template>

<script>
import data from '../siteContent.json'

export default {
   name: 'Section1',
   data(){
      return {
         section1_data: []
      }
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
   padding: 0;
   height: 8rem;
   background-color: var(--header-bg);
   border-top: 1px #E9ECEF solid;

   div {
      height: 100%;
   }

   img {
      height: 1.5rem;
   }
}

</style>
