
<template>
  <h1 style="color: blue;">Projects</h1>
  <div class="row justify-content-between">
    <project-card 
    v-for="project in projects"
    :key="project.id" 
    :project="project"
    class="col-3 mx-2 my-3"
    />
  </div>
</template>


<script>
  // import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios';
import ProjectCard from './components/ProjectCard.vue'  


  export default{
    name: 'App',
    components: {
      ProjectCard
    },
    data(){
      return{
        projects: []
      }
    },
    mounted(){
      axios.get('http://localhost:8000/api/v1/projects')
        .then(res => {
          this.projects = res.data.projects;
          console.log(JSON.stringify(this.projects, null, 2));
        })
        .catch(err => console.error(err));
    }
  }
</script>