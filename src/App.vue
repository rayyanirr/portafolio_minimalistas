<script setup>

import Hero from './components/sections/Hero.vue'
import About from './components/sections/About.vue'
import Experience from './components/sections/Experience.vue'
import Education from './components/sections/Education.vue'
import Proyects from './components/sections/Proyects.vue'
import Skills from './components/sections/Skills.vue'
import KeyboardManager from './components/KeyBoardManager.vue'

</script>


<template>
  <main>
    <Hero />
    <About />
    <Experience />
    <!-- <Education /> -->
    <Proyects />
    <Skills />
  </main>

  <KeyboardManager />
</template>

<style scoped>
main {
  padding: 4rem;
  margin: auto;
  width: 100%;
}
</style>