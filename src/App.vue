<script setup>
import Download from './components/Download.vue';
import Features from './components/Features.vue';
import Hero from './components/Hero.vue';
import Navbar from './components/Navbar.vue';
import FAQ from './components/FAQ.vue'
import SignUp from './components/SignUp.vue';
import Footer from './components/Footer.vue';


</script>

<template>
  <header>
    <Navbar />
  </header>

  <main>
    <Hero />
    <Features />
    <Download />
    <FAQ />
    <SignUp />
  </main>
  <footer>
    <Footer />
  </footer>
</template>

<style scoped>

</style>
