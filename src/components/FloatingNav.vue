<script setup>
defineProps({
  items: {
    type: Array,
    required: true
  }
})

const goToSection = (id) => {
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth', block: 'start' })
}
</script>

<template>
  <nav class="floating-nav" aria-label="Navegación de la invitación">
    <button
      v-for="item in items"
      :key="item.id"
      class="nav-dot"
      type="button"
      :aria-label="`Ir a ${item.label}`"
      @click="goToSection(item.id)"
    >
      <span>{{ item.label }}</span>
    </button>
  </nav>
</template>
