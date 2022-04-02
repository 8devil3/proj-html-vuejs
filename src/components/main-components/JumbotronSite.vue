<template>
<section>
   <div class="container row justify-between align-center">
      <div class="left col">
         <div class="badge">Development</div>
         <h1>a complete developer toolset</h1>
         <p>Launch your campaign and benefit from our expertise on designing an managing conversion centered bootstrap4 html page</p>
         <div class="row align-center">
            <button class="btn btn-primary">get started</button>
            <button class="btn btn-secondary">documentation</button>
         </div>
         <p class="version">Current Version v2.6.0</p>
      </div>
      <div class="right">
         <img src="../../assets/img/about.png" alt="About">
      </div>
   </div>
</section>
</template>

<script>
export default {
   name: 'JumbotronSite'

}
</script>

<style lang="scss" scoped>
section {
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
