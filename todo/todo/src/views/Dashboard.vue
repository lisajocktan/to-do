<template>
  <div class="dashboard">
    <h2 class="sub">Dashboard</h2>
   <v-container class="my-5">
    <v-icon color="grey">mdi-sort
    </v-icon>
    <v-btn flat variant="plain">
      <v-icon>mdi-folder</v-icon>
    <span class="caption text-lowercase"  @click="sortBy('title')">By Project Name</span>
    <v-tooltip
        activator="parent"

        location="bottom"
      >Tooltip</v-tooltip>
    </v-btn>
    <v-btn flat  variant="plain">
      <v-icon>mdi-account</v-icon>
    <span class="caption text-lowercase" @click="sortBy('person')">By Person</span>
    </v-btn>

    <v-layout></v-layout>
 <v-card class="pa-3" v-for="project in projects" :key="project.title">
  <v-row :class="`pa-3 project ${project.status}                                                                                                                                                                             tus}`">
   <v-col sm="4"
        md="4" >
    <div class="font-weight-medium">Project Title</div>
    <div>{{project.title}}</div>
   </v-col> 
   <v-col sm="4"
        md="4" >
    <div class="font-weight-medium">Person</div>
    <div>{{project.person}}</div>
   </v-col> 
   <v-col sm="2"
        md="2" >
    <div class="font-weight-medium">Due By</div>
    <div>{{project.due}}</div>
   </v-col> 
   <v-col sm="2" md="2" >
    <div>
      <v-chip :class="`pa-3 project ${project.status}`">{{project.status}}</v-chip>
      </div>
   </v-col> 
  </v-row>
 </v-card>
    
   </v-container>
  </div>
</template>

<script>
export default {
name: 'DashboardPage',
 data() {
    return {
      projects: [
        { title: 'Design a new website', person: 'The Net Ninja', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Code up the homepage', person: 'Chun Li', due: '10th Jan 2019', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Design video thumbnails', person: 'Ryu', due: '20th Dec 2018', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Create a community forum', person: 'Gouken', due: '20th Oct 2018', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
      ]
    }
  },
   methods: {
    sortBy(prop) {
      this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
    }
  }
}
</script>

<style scoped>

.project.complete{
  border-left: 4px solid #3CD1C2;
}
.project.ongoing{
  border-left: 4px solid orange
}
.project.overdue{
  border-left: 4px solid tomato;
}
.v-chip.complete{
  background: #3cd1c2;
}
.v-chip.ongoing{
  background: #ffaa2c;
}
.v-chip.overdue{
  background: #f83e70;
}

</style>