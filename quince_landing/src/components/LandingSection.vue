<script setup>
defineProps({
  id: {
    type: String,
    required: true
  },
  image: {
    type: String,
    required: true
  },
  alt: {
    type: String,
    default: ''
  }
})
</script>

<template>
  <section :id="id" class="visual-section reveal-section">
    <div class="section-frame neon-frame">
      <img class="section-image" :src="image" :alt="alt" loading="lazy" />
    </div>
  </section>
</template>
