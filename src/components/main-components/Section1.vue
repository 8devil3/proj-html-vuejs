<template>
<section>
   <div class="container row justify-between align-center">
      <img v-for="img in imgBrands" :key="img.id" :src="require('../../assets/img/brands/' + img.fileName)" :alt="img.alt">
   </div>
</section>
</template>

<script>
export default {
   name: 'Section2',
   data(){
      return {
         imgBrands: [
            {
               id: 1,
               fileName: 'amazon.svg',
               alt: 'Amazon'
            },
            {
               id: 2,
               fileName: 'google.svg',
               alt: 'Google'
            },
            {
               id: 3,
               fileName: 'lenovo.svg',
               alt: 'Lenovo'
            },
            {
               id: 4,
               fileName: 'paypal.svg',
               alt: 'PayPal'
            },
            {
               id: 5,
               fileName: 'shopify.svg',
               alt: 'Shopify'
            },
            {
               id: 6,
               fileName: 'spotify.svg',
               alt: 'Spotify'
            }
         ]
      }
   }

}
</script>

<style lang="scss" scoped>
section {
   height: 8rem;
   background-color: #f8f9fc;
   border-top: 1px #E9ECEF solid;

   div {
      height: 100%;
   }

   img {
      height: 1.5rem;
   }
}

</style>
