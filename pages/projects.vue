<script setup> 
 import project1 from '/pages/project1.vue';
 import project2 from '/pages/project2.vue';
 import project3 from '/pages/project3.vue';
</script>

<template>


  <div class="text">
    <h1>PROJECTS</h1>
  </div>

  <div class="projects">
    <div class="project">
      <img src="/assets/photos/prj1/prj1_6.png" alt="project1" class="project-photo" >
      <NuxtLink to="/project1">
        <h3>Dreamy</h3>
      </NuxtLink>
    </div>

    <div class="project">
      <img src="/assets/photos/prj2/prj2_2.png" alt="project2" class="project-photo" >
      <NuxtLink to="/project2">
        <h3>Feely</h3>
      </NuxtLink>
    </div>

    <div class="project">
      <img src="/assets/photos/prj3/prj3_1.jpg" alt="project3" class="project-photo" >
      <NuxtLink to="/project3">
        <h3>Formal</h3>
      </NuxtLink>
    </div>
</div>
  
</template>