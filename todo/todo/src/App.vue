<template>
  <v-app class="app">
    <Navbar />
    <v-main class="mx-5 mt-3">
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
export default {
  name: 'App',
  components: {
    Navbar,
},
  data: () => ({
    //
  }),
}
</script>
<style>
.app{
  background-color:rgb(223, 223, 222);
}



</style>