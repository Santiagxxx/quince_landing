<script setup>
import LandingSection from './components/LandingSection.vue'
import RsvpSection from './components/RsvpSection.vue'
import FloatingNav from './components/FloatingNav.vue'
import { sections } from './data/sections'

const navItems = [
  ...sections.map(({ id, label }) => ({ id, label })),
  { id: 'te-esperamos', label: 'Te esperamos' }
]
</script>

<template>
  <main class="landing" aria-label="Invitación digital Los 15 de Cata">
    <FloatingNav :items="navItems" />

    <LandingSection
      v-for="section in sections"
      :key="section.id"
      :id="section.id"
      :image="section.image"
      :alt="section.alt"
    />

    <RsvpSection id="te-esperamos" />
  </main>
</template>
