<template>
<section>
   <div class="container">
      <h2>Key Features</h2>
      <p>Start working with <strong>Landrick</strong> that can provide everything you need to generate awareness, drive traffic, connect.</p>
      <div class="card-wrapper row justify-between">
         <card-key-features v-for="card in cards" :key="card.id" :card="card"/>
      </div>
   </div>
</section>
</template>

<script>
import CardKeyFeatures from './CardKeyFeatures.vue'

export default {
   name: 'Section1',
   components: {
      CardKeyFeatures
   },
   data(){
      return {
         cards: [
            {
               id: 1,
               title: 'modular',
               text: 'Composed in a pseudo-Latin language which more or less corresponds.',
               link: '#',
               icon: 'fa-layer-group'
            },
            {
               id: 2,
               title: 'responsive',
               text: 'Composed in a pseudo-Latin language which more or less corresponds.',
               link: '#',
               icon: 'fa-mobile-screen'
            },
            {
               id: 3,
               title: 'customizable',
               text: 'Composed in a pseudo-Latin language which more or less corresponds.',
               link: '#',
               icon: 'fa-location-crosshairs'
            },
            {
               id: 4,
               title: 'scalable',
               text: 'Composed in a pseudo-Latin language which more or less corresponds.',
               link: '#',
               icon: 'fa-maximize'
            },
         ]
      }
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
