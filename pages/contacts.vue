<template>
  <section class="contact">
    <h1>Contact Me</h1>

    <!-- Form setup with Netlify integration -->
    <form 
      name="contact" 
      method="POST" 
      data-netlify="true" 
      @submit.prevent="getAge"
    >
      <div class="form-row">
        <input v-model="name" type="text" placeholder="Name" required />
        <input type="email" placeholder="Email" required />
      </div>

      <textarea placeholder="Message" rows="5" required></textarea>

      <button type="submit">Send</button>
    </form>

    <!-- Display the predicted age -->
    <div v-if="predictedAge !== null">
      <p>Based on your name, the estimated age is: {{ predictedAge }} years old.</p>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Define state variables
const name = ref('')
const predictedAge = ref(null)

// Function to fetch age prediction from Agify API
const getAge = async () => {
  try {
    const res = await fetch(`https://api.agify.io/?name=${name.value}`)
    const data = await res.json()
    predictedAge.value = data.age
  } catch (error) {
    console.error('Error fetching age prediction:', error)
  }
}
</script>