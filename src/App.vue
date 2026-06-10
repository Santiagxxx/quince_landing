<script setup>
import FloatingNav from "./components/FloatingNav.vue";
import HeroSection from "./components/HeroSection.vue";
import About from "./components/AboutCataSection.vue";
import Evento from './components/EventoSection.vue';
import DressCode from './components/DressCodeSection.vue';
import Album from './components/SharedAlbumSection.vue';
import Sobres from './components/EnvelopeSection.vue';
import Final from './components/FinalSection.vue';


</script>

<template>
  <main class="min-h-screen bg-black text-white overflow-x-hidden">
    <FloatingNav />
    <HeroSection />
    <About />
    <Evento />
    <DressCode/>
    <Album />
    <Sobres />
    <Final />
  </main>
</template>
