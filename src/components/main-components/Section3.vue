<template>
<section>
   <div class="container">
      <div class="col-12 col-lg-6 text-center mx-auto">
         <p><strong>{{ section3_data.subtitle }}</strong></p>
         <h2>{{ section3_data.title }}</h2>
         <p v-html="section3_data.content"></p>
         <div>
            <div class="code">
               <ul class="nav nav-pills nav-justified mb-3 btn-lang-wrapper" id="pills-tab" role="tablist">
                  <li role="presentation" class="nav-item">
                     <button class="nav-link btn-lang active" id="pills-npm-tab" data-bs-toggle="pill" data-bs-target="#pills-npm" type="button" role="tab" aria-controls="pills-npm" aria-selected="true">npm</button>
                  </li>
                  <li role="presentation" class="nav-item">
                     <button class="nav-link btn-lang" id="pills-nuget-tab" data-bs-toggle="pill" data-bs-target="#pills-nuget" type="button" role="tab" aria-controls="pills-nuget" aria-selected="false">nuget</button>
                  </li>
                  <li role="presentation" class="nav-item">
                     <button class="nav-link btn-lang" id="pills-spm-tab" data-bs-toggle="pill" data-bs-target="#pills-spm" type="button" role="tab" aria-controls="pills-spm" aria-selected="false">spm</button>
                  </li>
                  <li role="presentation" class="nav-item">
                     <button class="nav-link btn-lang" id="pills-github-tab" data-bs-toggle="pill" data-bs-target="#pills-github" type="button" role="tab" aria-controls="pills-github" aria-selected="false">github</button>
                  </li>
               </ul>
               <div class="tab-content" id="pills-tabContent">
               <div class="tab-pane fade show active" id="pills-npm" role="tabpanel" aria-labelledby="pills-npm-tab">
                  <p><span>$</span> npm install <span>-g</span> claps.js</p>
               </div>
               <div class="tab-pane fade" id="pills-nuget" role="tabpanel" aria-labelledby="pills-nuget-tab">
                  <p><span>$</span> nuget install <span>-g</span> claps.js</p>
               </div>
               <div class="tab-pane fade" id="pills-spm" role="tabpanel" aria-labelledby="pills-spm-tab">
                  <p><span>$</span> spm install <span>-g</span> claps.js</p>
               </div>
               <div class="tab-pane fade" id="pills-github" role="tabpanel" aria-labelledby="pills-github-tab">
                  <p><span>$</span> github install <span>-g</span> claps.js</p>
               </div>
               </div>
            </div>
            <div class="d-flex align-items-center flex-wrap">
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
            color: var(--code-btn-text);
            border: 0;
            background: transparent;
            padding: 0.5rem 1rem;
            border-radius: 0.3rem;
            flex-grow: 1;
            text-transform: lowercase;
         }

         .active {
            background-color: var(--code-bg);
         }
      }

      p {
         text-align: left;
         margin: 0;
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
