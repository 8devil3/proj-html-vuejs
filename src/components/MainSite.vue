<template>
<main>
   <jumbotron-site />
   <section-1 />
   <section-2 />
   <section-3 />
   <section-4 />
   <section-5 />
   <section-6 />
</main>
</template>

<script>
import JumbotronSite from './main-components/JumbotronSite.vue'
import Section1 from './main-components/Section1.vue'
import Section2 from './main-components/Section2.vue'
import Section3 from './main-components/Section3.vue'
import Section4 from './main-components/Section4.vue'
import Section5 from './main-components/Section5.vue'
import Section6 from './main-components/Section6.vue'

export default {
  components: { JumbotronSite, Section1, Section2, Section3, Section4, Section5, Section6 },
   name: 'MainSite'
}
</script>

<style lang="scss" scoped>

</style>
