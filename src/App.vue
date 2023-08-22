
<template>
  <h1>Hello, World!</h1>
</template>


<script>
  // import HelloWorld from './components/HelloWorld.vue'
  import axios from 'axios';



  export default{
    name: 'App',
    mounted(){
      axios.get('http://localhost:8000/api/v1/projects')
        .then(res => {
          console.log(res.data);
        })
        .catch(err => console.error(err));
    }
  }
</script>