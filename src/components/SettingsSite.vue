<template>
<div class="settings-wrapper d-flex flex-row-reverse">
   <div class="label d-flex align-items-center justify-content-center">
      <i class="fa-solid fa-gear"></i>
   </div>
   <div class="settings d-flex flex-column px-4 py-3">
      <p class="mb-2">Colors</p>
      <div class="d-flex">
         <button class="me-1 color blue"></button>
         <button class="me-1 color red"></button>
         <button class="me-1 color green"></button>
         <button class="me-1 color violet"></button>
      </div>
      <hr>
      <div class="d-flex align-items-center">
         <p class="m-0">Dark mode</p>
      <button class="ms-2 btn-dark-mode" @click="setDarkMode()"><i class="fa-solid fa-circle-half-stroke"></i></button>
      </div>
      <hr>
      <p class="m-0">Font size</p>
      <div class="font-size d-flex">
         <button class="font-big me-1 btn-dark-mode">A</button>
         <button class="font-medium me-1 btn-dark-mode">A</button>
         <button class="font-small me-1 btn-dark-mode">A</button>
      </div>
   </div>
</div>
</template>

<script>
export default {
   name: 'SettingsSite',
   data(){
      return {
         darkMode: false,
         root: null
      }
   },
   methods: {
      setDarkMode(){ //dark mode
         this.root.classList.toggle('dark-mode')
      }
   },
   mounted(){
      this.root = document.documentElement
   }
}
</script>

<style lang="scss" scoped>
.settings-wrapper {
   position: absolute;
   top: 8rem;
   left: 0;

   .label {
      height: 2.5rem;
      width: 2.5rem;
      color: var(--primary);
      border-radius: 0 50% 50% 0;
      box-shadow: 0 0 4px 0 #0000001a;
      background-color: #fff;
   }

   .settings {
      background-color: #fff;
      box-shadow: 0 0 4px 0 #0000001a;

      .color {
         width: 1.5rem;
         height: 1.5rem;
         border-radius: 50%;
         border: 1px var(--dark-blue) solid;
      }

      .blue {
         background-color: var(--primary);
      }

      .red {
         background-color: var(--red);
      }

      .green {
         background-color: var(--green);
      }

      .violet {
         background-color: var(--violet);
      }

      .btn-dark-mode {
         border: 0;
         background: transparent;
         color: var(--dark-blue);
         font-size: 1.5rem;
         font-weight: 700;
      }

      .font-small {
         font-size: 0.8rem
      }

      .font-medium {
         font-size: 1rem;
      }

      .font-big {
         font-size: 1.2rem;
      }
   }
}
</style>