<template>
<section>
   <div class="container">
      <div class="top">
         <h2>{{ section5_data.title }}</h2>
         <p v-html="section5_data.content"></p>
      </div>
      <div class="row card-wrapper">
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
   .top {
      width: 50%;
      margin: 0 auto;
      text-align: center;

      p {
         margin: 1rem 0 4rem 0;
      }
   }

   .card-wrapper {
      margin: 0 -1rem;
   }
}
</style>
