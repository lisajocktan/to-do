<template>
 <div class="team" >
    <h2 class="subheading">My Team</h2>
   <v-container class="my-4">
    <v-row>
     <v-col v-for="person in team" :key="person.name">
       <v-card>
         <v-responsive class="pt-4 px-3">
              <v-avatar size="100" class="grey lighten-2">
                <img :src="person.avatar">
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="subheading">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn flat color="grey">
                <v-icon small left>mdi-message</v-icon>
                <span class="">Message</span>
              </v-btn>
            </v-card-actions>
     </v-card>
     </v-col>







    </v-row>
   </v-container>
  </div>
</template>

<script>
export default {
  name: 'TeamPage',
   data() {
    return {
      team: [
         { name: 'The Net Ninja', role: 'Web developer', avatar: '/avatar-1.png' },
        { name: 'Ryu', role: 'Graphic designer', avatar: '/avatar-2.png' },
        { name: 'Chun Li', role: 'Web developer', avatar: '/avatar-3.png' },
        { name: 'Gouken', role: 'Social media maverick', avatar: '/avatar-4.png' },
        { name: 'Yoshi', role: 'Sales guru', avatar: '/avatar-5.png'}

      ]
    }
  }

}
</script>

<style>
/* .team{
  background-color: rgb(236, 250, 233);
  color:rgb(3, 3, 3);
 
} */
.subheading{
  font-size: larger;
  color: rgb(5, 5, 5);
}

</style>