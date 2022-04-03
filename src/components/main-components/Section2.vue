<template>
<section>
   <div class="container">
      <h2>{{ section2_data.title }}</h2>
      <p v-html="section2_data.content"></p>
      <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 g-5">
         <card-key-features v-for="card in section2_data.cards" :key="card.id" :card="card"/>
      </div>
   </div>
</section>
</template>

<script>
import data from '../siteContent.json'
import CardKeyFeatures from './CardKeyFeatures.vue'

export default {
   name: 'Section2',
   components: {
      CardKeyFeatures
   },
   data() {
      return {
         section2_data: {}
      }
   },
   methods: {
      getData(){
         this.section2_data = data.section_2
      }
   },
   created(){
      this.getData()
   }
}
</script>

<style lang="scss" scoped>
@import '../../assets/scss/_colors.scss';
@import '~bootstrap';

section {
   p {
      max-width: 80rem;
      margin: 2rem 0 4rem 0;
   }
}
</style>
