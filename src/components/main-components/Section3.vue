<template>
<section>
   <div class="wrapper">
      <p><strong>Quickstart</strong></p>
      <h2>Awesome isn't it? Let's dive in!</h2>
      <p>Start working with <strong>Landrick</strong> that can provide everything you need to generate awareness, drive traffic, connect.</p>
      <div class="col">
         <div class="code">
            <div class="btn-lang-wrapper row align-center">
               <div class="active btn-lang row align-cener justify-center">npm</div>
               <div class="btn-lang row align-cener justify-center">nuget</div>
               <div class="btn-lang row align-cener justify-center">spm</div>
               <div class="btn-lang row align-cener justify-center">github</div>
            </div>
            <p><span>$</span> npm install <span>-g</span> claps.js</p>
         </div>
         <div class="row align-center">
            <p class="features"><i class="fa-regular fa-circle-check"></i>Organize your data</p>
            <p class="features"><i class="fa-regular fa-circle-check"></i>Work with any team</p>
         </div>
      </div>
   </div>
</section>
</template>

<script>
export default {
   name: 'Section3'
}
</script>

<style lang="scss" scoped>
section {
   .wrapper {
      margin: 0 auto;
      max-width: 50%;
      text-align: center;
   }

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
