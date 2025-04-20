<template>
    <div class="index-container">
      <img src="/assets/photos/emily.jpg" alt="My Photo" class="index-image">
      <div class="index-text">
        <h1>Emily <br> Palm <br> </h1>
      </div>
    </div>
  
    <div class="bio">
      <h1>BIO</h1>
      <p>
        Hi, I'm Emily Palm — a passionate creative spirit with a love for bringing ideas to life! 
        I'm currently building my own filmography company, where I focus on crafting visuals that 
        truly make people feel.<br><br>
        I'm outgoing, kind, and always chasing new ways to express creativity. For me, every frame 
        is a chance to tell a story — and I can't wait to share mine with the world.
      </p>
    </div>
  
    <div class="quote-section">
      <h2>Inspirational Quote:</h2>
      <p v-if="advice">{{ advice }}</p>
      <p v-else>Loading quote...</p>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue'
  
  const advice = ref('')
  
  onMounted(async () => {
    try {
      const res = await fetch('https://api.adviceslip.com/advice')
      const data = await res.json()
      advice.value = data.slip.advice
    } catch (error) {
      console.error("Failed to fetch advice:", error)
    }
  })
  </script>