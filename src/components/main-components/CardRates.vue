<template>
<article>
   <div>
      <div v-show="card.best" class="badge-best-wrapper row align-center justify-center">
         <div class="badge-shadow"><div class="badge-best">Best</div></div>
      </div>

      <div class="badge">{{ card.plan }}</div>
      <p class="price">{{ card.price }}</p>
      <p>{{ card.period }}</p>
      <p>{{ card.description }}</p>
      <ul>
         <li v-for="item in card.features" :key="item.id">{{ item.feature }}</li>
      </ul>
      <button class="btn btn-primary">buy now</button>
      <p>*No credit card required</p>
   </div>
</article>
</template>

<script>
export default {
   name: 'CardRates',
   props: {
      card: Object
   }
}
</script>

<style lang="scss" scoped>
article {
   > div{
      padding: 1.5rem;
      box-shadow: 0 0 3px var(--shadows);
      border-radius: 0.9rem;
      border-bottom: 3px #adb5bd solid;
      transition: transform 0.3s, border 0.3s, box-shadow 0.3s;
      position: relative;

      &:hover {
         transform: scale(1.05);
         border-bottom: 3px var(--primary) solid;
         box-shadow: 0 4px 16px 0 var(--shadows);
      }
   }

   .badge-best-wrapper {
      position: absolute;
      top: -0.25rem;
      right: -0.25rem;
      height: 4.25rem;
      width: 4.25rem;
      overflow: hidden;

      .badge-shadow {
         flex-shrink: 0;
         position: relative;
         height: 1.25rem;
         width: 86px;
         border-top: 6px transparent solid;
         border-left: 6px var(--dark-orange) solid;
         border-right: 6px var(--dark-orange) solid;
         border-bottom: 6px transparent solid;
         transform: rotate(45deg) translate(0, -50%);
         z-index: 10;
         
         .badge-best {
            position: absolute;
            flex-shrink: 0;
            height: 1.25rem;
            width: 86px;
            background-color: var(--orange);
            font-size: 0.8rem;
            color: #fff;
            text-align: center;         
            top: -12px;
            left: -6px;
         }
      }
   }

   .badge {
      padding: 0.5rem 1rem;
      background-color: var(--badge-bg);
      border: 1px var(--badge-border) solid;
      border-radius: 500px;
      color: var(--badge-text);
      font-size: 0.8rem;
      font-weight: 700;
      width: fit-content;
   }

   .price {
      font-size: 2rem;
      color: var(--prices);
      font-weight: 700;
      margin: 0.5rem 0;
   }

   h3 {
      text-transform: capitalize;
   }

   p {
      line-height: 150%;
      margin: 0.5rem 0;
   }

   ul {
      margin: 2rem 0;

      li {
         margin: 0.25rem 0;

         &::before {
            content: '\f058';
            font-family: 'Font Awesome 6 Free';
            font-weight: 40;
            font-size: 1rem;
            color: var(--primary);
            margin-right: 0.5rem;
            vertical-align: middle;
         }
      }
   }

   button {
      width: 100%;
   }
}

</style>
