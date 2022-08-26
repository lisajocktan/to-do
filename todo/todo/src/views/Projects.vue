<template>
  <div class="projects" >
    <h2 class="subheading">Projects</h2>
       <v-expansion-panels>
      <v-expansion-panel
        v-for="i in 3"
        :key="i"
        title="Item"
        text="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."
      ></v-expansion-panel>
    </v-expansion-panels>
  </div>
   <Popup />
</template>

<script>
import Popup from '@/components/Popup.vue'
export default {
  name: 'ProjectPage',
  components: {
  Popup
},
}
</script>

<style>
.projects{
  background-color: rgb(243, 255, 239);
  color:rgb(3, 3, 3);
 
}
.subheading{
  font-size: larger;
  color: rgb(5, 5, 5);
}
</style>