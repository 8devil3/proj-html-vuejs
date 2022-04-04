<template>
<div class="settings-wrapper d-flex flex-row-reverse" id="settings">
   <div class="label d-flex align-items-center justify-content-center" @click="openSettingsPanel()">
      <i class="fa-solid fa-gear"></i>
   </div>
   <div class="settings d-flex flex-column px-4 py-3">
      <p class="mb-2">Colors</p>
      <div class="d-flex">
         <button class="me-1 color blue" @click="setColors('blue')"></button>
         <button class="me-1 color red" @click="setColors('red')"></button>
         <button class="me-1 color green" @click="setColors('green')"></button>
         <button class="me-1 color violet" @click="setColors('violet')"></button>
      </div>
      <hr>
      <div class="d-flex align-items-center">
         <p class="m-0">Dark mode</p>
      <button class="ms-2 btn-dark-mode" @click="setDarkMode()"><i class="fa-solid fa-circle-half-stroke"></i></button>
      </div>
      <hr>
      <p class="m-0">Font size</p>
      <div class="font-size d-flex align-items-center">
         <button @click="setFontSize('large')" class="font-big me-1 btn-dark-mode">A</button>
         <button @click="setFontSize('default')" class="font-medium me-1 btn-dark-mode">A</button>
         <button @click="setFontSize('small')" class="font-small me-1 btn-dark-mode">A</button>
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
         root: null,
         settingsPanel: null
      }
   },
   methods: {
      openSettingsPanel(){
         this.settingsPanel.classList.toggle('settings-open')
      },
      setDarkMode(){
         this.root.classList.toggle('dark-mode')
         this.darkMode = !this.darkMode
         this.$emit('setDarkMode', this.darkMode)
      },
      setFontSize(fs) {
         switch (fs) {
            case 'small':
               this.root.style.fontSize = '13px';
               break;
            case 'default':
               this.root.style.fontSize = '16px';
               break;
            case 'large':
               this.root.style.fontSize = '18px';
               break;
         }
      },
      setColors(color){
         switch (color) {
            case 'blue':
               this.root.classList.add('blue')
               this.root.classList.remove('red','green','violet')
               break;
            case 'red':
               this.root.classList.add('red')
               this.root.classList.remove('blue','green','violet')
               break;
            case 'green':
               this.root.classList.add('green')
               this.root.classList.remove('red','blue','violet')
               break;
            case 'violet':
               this.root.classList.add('violet')
               this.root.classList.remove('blue','green','red')
               break;
         
            default:
               this.root.classList.add('blue')
               this.root.classList.remove('red','green','violet')
               break;
         }
      }
   },
   mounted(){
      this.root = document.documentElement
      this.settingsPanel = document.querySelector('#settings')
   }
}
</script>

<style lang="scss" scoped>
.settings-wrapper {
   position: fixed;
   top: 3.5rem;
   left: -172px;
   z-index: 10;
   transition: left 0.4s ease-in-out;

   .label {
      height: 2.5rem;
      width: 2.5rem;
      color: var(--primary);
      border-radius: 0 50% 50% 0;
      box-shadow: 0 0 4px 0 var(--shadows);
      background-color: var(--settings-bg);
      cursor: pointer;
   }

   .settings {
      background-color: var(--settings-bg);
      box-shadow: 0 0 4px 0 var(--shadows);

      .color {
         width: 1.5rem;
         height: 1.5rem;
         border-radius: 50%;
         border: 1px var(--headings) solid;
      }

      .blue {
         background-color: #2f55d4;
      }

      .red {
         background-color: #e43f52;;
      }

      .green {
         background-color: #2eca8b;
      }

      .violet {
         background-color: #7952B3;
      }

      .btn-dark-mode {
         border: 0;
         background: transparent;
         color: var(--headings);
         font-size: 1.5rem;
         font-weight: 700;
      }

      .font-small {
         font-size: 13px
      }

      .font-medium {
         font-size: 16px;
      }

      .font-big {
         font-size: 20px;
      }
   }
}

.settings-open {
   left: 0;
}
</style>