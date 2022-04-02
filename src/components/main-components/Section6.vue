<template>
<section>
   <div class="wrapper">
      <h2>Want to be among the first to find out?</h2>
      <p>Start working with Landrick that can provide everything you need to generate awareness, drive traffic, connect.</p>
      <div class="input-wrapper">
         <input type="email" id="email" placeholder="Email Addresss">
         <button class="btn btn-primary">get started</button>
      </div>
   </div>
</section>
</template>

<script>
export default {
   name: 'Section6'
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
