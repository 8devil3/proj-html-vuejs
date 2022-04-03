<template>
<article>
   <div class="icon row align-center justify-center">
      <i :class="card.fontAwesomeClasses"></i>
   </div>
   <h3>{{ card.title }}</h3>
   <p>{{ card.content }}</p>
   <a :href="card.link">read more</a>
</article>
</template>

<script>
export default {
   name: 'CardKeyFeatures',
   props: {
      card: Object
   }
}
</script>

<style lang="scss" scoped>
article {
   padding: 1.5rem;
   box-shadow: 0 0 4px 0 #0000001a;
   margin: 0 1rem;
   border-radius: 0.3rem;

   .icon {
      height: 4rem;
      width: 4rem;
      background-color: var(--icons-bg);
      border-radius: 0.3rem;
      color: var(--primary);
      font-size: 1.5rem;
      margin-bottom: 1.5rem;
   }

   h3 {
      text-transform: capitalize;
   }

   p {
      line-height: 150%;
      margin: 0.5rem 0 1.5rem 0;
   }

   a {
      display: block;
      color: var(--primary);
      font-weight: 700;
      text-transform: capitalize;

      &:hover {
         color: var(--primary-hover);
      }

      &::after {
         content: '\f054';
         font-size: 0.5rem;
         font-family: 'Font Awesome 6 Free';
         font-weight: 900;
         margin-left: 0.5rem;
         vertical-align: middle;
      }
   }
}

</style>
