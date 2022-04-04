<template>
<section>
   <div class="container">
      <div class="col-12 col-md-6 text-center mx-auto">
         <h2>{{ section5_data.title }}</h2>
         <p v-html="section5_data.content"></p>
      </div>
      <div class="row row-cols-1 row-cols-md-3 g-5">
         <card-rates v-for="card in section5_data.cards" :key="card.id" :card="card"/>
      </div>
   </div>
</section>
</template>

<script>
import data from '../siteContent.json'
import CardRates from './CardRates.vue'

export default {
  components: { CardRates },
   name: 'Section5',
   data(){
      return {
         section5_data: {}
      }
   },
   methods: {
      getData(){
         this.section5_data = data.section_5
      }
   },
   created(){
      this.getData()
   }
}
</script>

<style lang="scss" scoped>
section{
   p {
      margin: 1rem 0 4rem 0;
   }
}
</style>
