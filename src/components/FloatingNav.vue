<script setup>
const leftItems = [
  { label: 'Inicio', href: '#inicio' },
  { label: 'Cata', href: '#cata' },
  { label: 'El evento', href: '#evento' },
]

const rightItems = [
  { label: 'Dress-code', href: '#dress-code' },
  { label: 'Tu huella', href: '#tu-huella' },
  { label: 'Lluvia de sobres', href: '#lluvia-sobres' },
  { label: 'Te esperamos', href: '#te-esperamos' },
]
</script>

<template>
  <header class="fixed inset-x-0 top-0 z-50 h-[52px] bg-black/95">
    <nav class="nav-split">
      <!-- Grupo izquierdo -->
      <div class="nav-group nav-group-left">
        <template v-for="(item, index) in leftItems" :key="item.label">
          <a :href="item.href" class="nav-neon">
            {{ item.label }}
          </a>

          <span v-if="index !== leftItems.length - 1" class="nav-star">
            ✦
          </span>
        </template>
      </div>

      <!-- Grupo derecho -->
      <div class="nav-group nav-group-right">
        <template v-for="(item, index) in rightItems" :key="item.label">
          <a :href="item.href" class="nav-neon">
            {{ item.label }}
          </a>

          <span v-if="index !== rightItems.length - 1" class="nav-star">
            ✦
          </span>
        </template>
      </div>
    </nav>
  </header>
</template>