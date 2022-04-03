<template>
<section>
   <div class="wrapper">
      <h2>{{ section6_data.title }}</h2>
      <p v-html="section6_data.content"></p>
      <div class="input-wrapper">
         <input type="email" id="email" :placeholder="section6_data.inputPlaceholder">
         <button class="btn btn-primary">{{ section6_data.btnSubmitTxt }}</button>
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
   .wrapper {
      margin: 0 auto;
      text-align: center;
      max-width: 35rem;
   }

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
         right: 0.4rem;
         transform: translate(0, -50%);
         border-radius: 500px;
      }
   }
}
</style>
