<script setup>
import Navbar from './components/Navbar.vue'
import Header from './components/Header.vue'
import About from './components/About.vue'
import Services from './components/Services.vue'
</script>

<template>
  <div class="min-h-screen bg-light text-primary selection:bg-primary selection:text-light font-space-grotesk">
    <Navbar />
    <Header />
    <About />
    <Services />
  </div>
</template>