<template>
<section>
   <div class="container">
      <div class="row row-cols-1 row-cols-md-2 align-items-center">
         <div class="left col">
            <div class="badge">{{ jumbotronData.badgeText }}</div>
            <h1>{{ jumbotronData.title }}</h1>
            <p>{{ jumbotronData.content }}</p>
            <div class="d-flex align-items-center">
               <button class="btn btn-primary">{{ jumbotronData.btn1txt }}</button>
               <button class="btn btn-outline-primary">{{ jumbotronData.btn2txt }}</button>
            </div>
            <p class="version">{{ jumbotronData.ver }}</p>
         </div>
         <div class="right col">
            <img :src="require('../../assets/img/' + jumbotronData.rightImgFileName)" :alt="jumbotronData.rightImgAlt">
         </div>
      </div>
   </div>
</section>
</template>

<script>
import data from '../siteContent.json'

export default {
   name: 'JumbotronSite',
   data(){
      return {
         jumbotronData: []
      }
   },
   methods: {
      getData(){
         this.jumbotronData = data.jumbotron
      }
   },
   created(){
      this.getData()
   }
}
</script>

<style lang="scss" scoped>
section {
   background-color: var(--header-bg);

   h1 {
      text-transform: capitalize;
      font-size: 2.8rem;
      font-weight: 800;
   }

   p {
      font-size: 1.1rem;
      margin: 2rem 0;
   }

   .version {
      margin-top: 1rem;
      font-size: 1rem;
   }

   button {
      margin-right: 1rem;
   }

   .badge {
      text-transform: capitalize;
      padding: 0.25rem 0.5rem;
      margin-bottom: 1rem;
      background-color: var(--badge-bg);
      border: 1px var(--badge-border) solid;
      border-radius: 500px;
      color: var(--badge-text);
      font-size: 0.8rem;
      font-weight: 700;
      width: fit-content;
   }

   img {
      width: 100%;
      height: 100%;
      object-fit: contain;
   }
}

</style>
