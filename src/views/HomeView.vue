<template>
  <div class="bg-base-blue min-h-screen">
    <Header />
    <HeroSection />
    <Education />
    <Certificate />
    <AboutMe />
    <Experience />
    <Project />
    <Contact />
    <Footer />
  </div>
</template>

<script setup>
import AboutMe from '@/components/AboutMe.vue';
import Certificate from '@/components/Certificate.vue';
import Contact from '@/components/Contact.vue';
import Education from '@/components/Education.vue';
import Experience from '@/components/Experience.vue';
import Footer from '@/components/Footer.vue';
import Header from '@/components/Header.vue';
import HeroSection from '@/components/HeroSection.vue';
import Project from '@/components/Project.vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
import { onMounted } from 'vue';

onMounted(() => {
  AOS.init({
    duration: 1000,
    once: false,
    offset: 100
  })
})
</script>
