<template>
<section>
   <div class="container">
      <div class="top">
         <h2>Our rates for developer from Landrick team</h2>
         <p>Start working withs <strong>Landrick</strong> that can provide everything you need to generate awareness, drive traffic, connect.</p>
      </div>
      <div class="row card-wrapper">
         <card-rates v-for="card in cards" :key="card.id" :card="card"/>
      </div>
   </div>
</section>
</template>

<script>
import CardRates from './CardRates.vue'
export default {
  components: { CardRates },
   name: 'Section5',
   data(){
      return {
         cards: [
            {
               id: 1,
               plan: 'Basic',
               price: '$9.00',
               best: false,
               period: 'Per Month',
               description: 'All the basics for businesses that are just getting started.',
               features: [
                  {
                     id: 1,
                     feature: 'full access',
                  },
                  {
                     id: 2,
                     feature: 'enhanced security',
                  },
                  {
                     id: 3,
                     feature: 'surce files',
                  },
                  {
                     id: 4,
                     feature: '1 domain free',
                  },
                  {
                     id: 5,
                     feature: 'enhanced security',
                  }
               ]
            },
            {
               id: 2,
               plan: 'Business',
               price: '$39.00',
               best: true,
               period: 'Per Month',
               description: 'Better for growing businesses that want more customers.',
               features: [
                  {
                     id: 1,
                     feature: 'full access',
                  },
                  {
                     id: 2,
                     feature: 'enhanced security',
                  },
                  {
                     id: 3,
                     feature: 'surce files',
                  },
                  {
                     id: 4,
                     feature: '1 domain free',
                  },
                  {
                     id: 5,
                     feature: 'enhanced security',
                  }
               ]
            },
            {
               id: 3,
               plan: 'Enterprise',
               price: '$79.00',
               best: false,
               period: 'Per Month',
               description: 'Advanced features for pros who need more customization.',
               features: [
                  {
                     id: 1,
                     feature: 'full access',
                  },
                  {
                     id: 2,
                     feature: 'enhanced security',
                  },
                  {
                     id: 3,
                     feature: 'surce files',
                  },
                  {
                     id: 4,
                     feature: '1 domain free',
                  },
                  {
                     id: 5,
                     feature: 'enhanced security',
                  }
               ]
            },
         ]
      }
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
