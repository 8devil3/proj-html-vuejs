<template>
<section>
   <div class="container">
      <div class="col-12 col-lg-6 text-center mx-auto">
         <h2>{{ section6_data.title }}</h2>
         <p v-html="section6_data.content"></p>
         <div class="input-wrapper">
            <input type="email" id="email" :placeholder="section6_data.inputPlaceholder">
            <button class="btn btn-primary">{{ section6_data.btnSubmitTxt }}</button>
         </div>
      </div>
   </div>
</section>
</template>

<script>
import data from '../siteContent.json'

export default {
   name: 'Section6',
   data(){
      return {
         section6_data: []
      }
   },
   methods: {
      getData(){
         this.section6_data = data.section_6
      }
   },
   created(){
      this.getData()
   }
}
</script>

<style lang="scss" scoped>
section {

   p {
      margin: 2rem 0;
   }

   .input-wrapper {
      position: relative;

      input {
         padding: 1.2rem 1.5rem;
         border-radius: 500px;
         border: 1px #E9ECEF solid;
         width: 100%;
      }

      button {
         position: absolute;
         top: 50%;
         right: 0.5rem;
         transform: translate(0, -50%);
         border-radius: 500px;
         height: 3rem;
      }
   }
}
</style>
