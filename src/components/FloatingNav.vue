<script setup>
const navItems = [
  'Inicio',
  'Cata',
  'El evento',
  'Dress-code',
  'Tu huella',
  'Lluvia de sobres',
  'Te esperamos',
]
</script>

<template>
  <header class="relative z-50 h-[58px] bg-black">
    <nav class="mx-auto flex h-full max-w-[980px] items-center justify-center gap-4 px-4">
      <template v-for="(item, index) in navItems" :key="item">
        <a
          href="#"
          class="nav-neon"
        >
          {{ item }}
        </a>

        <span
          v-if="index !== navItems.length - 1"
          class="nav-star"
        >
          ✦
        </span>
      </template>
    </nav>
  </header>
</template>