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
                  <li role="presentation" class="nav-item" v-for="(code, index) in section3_data.codeLang" :key="code.id">
                     <button :class="index == 0 ? 'nav-link btn-lang active' : 'nav-link btn-lang'" :id="'pills-' + code.name + '-tab'" data-bs-toggle="pill" :data-bs-target="'#pills-' + code.name" type="button" role="tab" :aria-controls="'pills-' + code.name" aria-selected="true">{{ code.name }}</button>
                  </li>
               </ul>
               <div class="tab-content" id="pills-tabContent">

                  <div v-for="(code, index) in section3_data.codeLang" :key="code.id" :class="index == 0 ? 'tab-pane fade show active':'tab-pane fade'" :id="'pills-' + code.name" role="tabpanel" :aria-labelledby="'pills-' + code.name + '-tab'">
                     <p v-html="code.code"></p>
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
         section3_data: {},
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
