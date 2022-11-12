<template>
  <div class="home">
   <heroBanner/>
  </div>
</template>

<script>
// @ is an alias to /src
import heroBanner from '@/components/heroBanner.vue'
export default {
  name: 'HomeView',
  components: {
    heroBanner
  }
}
</script>
<style>
body{
  background-color: #21252C !important;
}
</style>