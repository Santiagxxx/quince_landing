<script setup>
import RsvpForm from './RsvpForm.vue'
</script>

<template>
  <section class="visual-section reveal-section rsvp-section">
    <div class="section-frame neon-frame rsvp-frame">
      <img
        class="section-image"
        src="/images/te-esperamos.png"
        alt="Sección Te esperamos con Cata sosteniendo flores y espacio para confirmar asistencia."
        loading="lazy"
      />

      <div class="rsvp-overlay" aria-label="Formulario de confirmación de asistencia">
        <RsvpForm />
      </div>
    </div>
  </section>
</template>
