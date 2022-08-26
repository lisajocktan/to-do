<template>
  <nav>
    <v-toolbar class="nav">
     <v-navigation-drawer app v-model="drawer" class="pt-5">
        <v-column align-center>
        <v-flex class="mt-5 ps-10" >
          <v-avatar size="100" >
            <img src="/lisa.jpg">
          </v-avatar>
          <p class="px-5" >Lisa Jocktan</p>
        </v-flex>
       
      </v-column>
    
      <v-divider></v-divider>

     <v-list class="px-4">
        <v-list-item v-for="link in links" :key="link.text" router :to="link.route" >
           <template v-slot:prepend >
          <v-icon :icon="link.icon" class="icon"></v-icon>
        </template>
          <v-list-item-content>
            <v-list-item-title v-text="link.text"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
       
      </v-list>
    </v-navigation-drawer >
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>
        <span class="font-weight-bold">TSMS</span>
        <span class="font-weight-light text-decoration-underline">Tempo</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn>
            <span class="pe-2">Sign Up</span>
            <v-icon>mdi-login</v-icon>
           </v-btn>
    </v-toolbar> 

    
  </nav>
</template>

<script>

export default {
name:'NavbarPage',


data(){
  return{
    drawer: false,
    links: [
      {icon: 'mdi-view-dashboard', text: 'Dashboard', route:'/'},
      {icon: 'mdi-folder', text: 'My Projects', route:'/projects'},
      {icon: 'mdi-account-outline', text: 'Team', route:'/team'},
    ]
  }
}
}
</script>

<style scoped>
.nav{
  background-color: rgb(15, 11, 11);
  color: white;
}
.icon{
  color: rgb(4, 5, 5);
}
.px-4{
   
  padding: 10px;
  box-shadow: 2px 5px 4px #888888;
}
</style>