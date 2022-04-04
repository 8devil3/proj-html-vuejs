<template>
<section>
   <div class="container">
      <div class="col-12 col-lg-6 text-center mx-auto">
         <p><strong>{{ section3_data.subtitle }}</strong></p>
         <h2>{{ section3_data.title }}</h2>
         <p v-html="section3_data.content"></p>
         <div>
            <div class="code">
               <div class="btn-lang-wrapper d-flex align-items-center">
                  <div class="active btn-lang d-flex align-items-center justify-content-center">npm</div>
                  <div class="btn-lang d-flex align-items-center justify-content-center">nuget</div>
                  <div class="btn-lang d-flex align-items-center justify-content-center">spm</div>
                  <div class="btn-lang d-flex align-items-center justify-content-center">github</div>
               </div>
               <p><span>$</span> npm install <span>-g</span> claps.js</p>
            </div>
            <div class="d-flex align-items-center">
               <p class="features"><i class="fa-regular fa-circle-check"></i> {{ section3_data.feat1 }}</p>
               <p class="features"><i class="fa-regular fa-circle-check"></i> {{ section3_data.feat2 }}</p>
            </div>
         </div>
      </div>
   </div>
</section>
</template>

<script>
import data from '../siteContent.json'

export default {
   name: 'Section3',
   data(){
      return {
         section3_data: {}
      }
   },
   methods: {
      getData(){
         this.section3_data = data.section_3
      }
   },
   created(){
      this.getData()
   }
}
</script>

<style lang="scss" scoped>
section {
   h2 {
      margin: 1rem 0 2rem 0;
   }

   .code {
      background-color: var(--code-bg);
      padding: 1.5rem;
      border-radius: 0.5rem;
      margin: 3rem 0 1rem 0;

      .btn-lang-wrapper {
         border: 1px #5F6978 solid;
         background-color: var(--code-btn-disabled);
         border-radius: 0.3rem;
         color: var(--code-btn-text);
         
         .btn-lang {
            padding: 0.5rem 1rem;
            border-radius: 0.3rem;
            flex-grow: 1;
         }

         .active {
            background-color: var(--code-bg);
         }
      }

      p {
         text-align: left;
         margin-top: 1rem;
         font-weight: 700;

         span {
            color: var(--green);
         }
      }
   }

   .features {
      margin-right: 3rem;
   }

   .fa-circle-check {
      color: var(--green);
      margin-right: 0.5rem;
   }
}

</style>
