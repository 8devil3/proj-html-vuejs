<template>
<section>
   <div class="container">
      <h2>{{ section2_data.title }}</h2>
      <p v-html="section2_data.content"></p>
      <div class="card-wrapper row justify-between">
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
section {

   p {
      width: 50%;
   }

   .card-wrapper {
      margin: 0 -1rem;
   }

   p {
      margin: 2rem 0 4rem 0;
   }
}
</style>
