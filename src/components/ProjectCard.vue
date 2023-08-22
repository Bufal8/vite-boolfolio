<template>
    <div class="card">
        <h1>{{project.name }}</h1>
        <p>{{ project.difficulty }}</p>
    </div>
</template>

<script>
export default{
    name: 'ProjectCard',
    props: {
        project:{
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped>
  
</style>