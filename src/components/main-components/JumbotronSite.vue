<template>
<section>
   <div class="container row justify-between align-center">
      <div class="left col">
         <div class="badge">{{ jumbotronData.badgeText }}</div>
         <h1>{{ jumbotronData.title }}</h1>
         <p>{{ jumbotronData.content }}</p>
         <div class="row align-center">
            <button class="btn btn-primary">{{ jumbotronData.btn1txt }}</button>
            <button class="btn btn-secondary">{{ jumbotronData.btn2txt }}</button>
         </div>
         <p class="version">{{ jumbotronData.ver }}</p>
      </div>
      <div class="right">
         <img :src="require('../../assets/img/' + jumbotronData.rightImgFileName)" :alt="jumbotronData.rightImgAlt">
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
   padding-bottom: 6rem;

   .left {
      width: 40%;

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
         padding: 0.25rem 0.5rem;
         background-color: var(--badge-bg);
         border: 1px var(--badge-border) solid;
         border-radius: 500px;
         color: var(--badge-text);
         font-size: 0.8rem;
         font-weight: 700;
         width: fit-content;
      }
   }

   .right {
      img {
         width: 100%;
         height: 100%;
         object-fit: contain;
      }
   }
}

</style>
