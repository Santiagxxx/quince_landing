<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'

const isSplit = ref(true)

let ticking = false

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

const getVisibleDoll = () => {
  const dolls = Array.from(document.querySelectorAll('[data-doll-over-nav="true"]'))

  return dolls.find((doll) => {
    const rects = doll.getClientRects()
    return rects.length > 0
  })
}

const getNavbarHeight = () => {
  if (window.innerWidth < 640) return 58
  if (window.innerWidth < 1024) return 68
  if (window.innerWidth < 1280) return 76
  return 86
}

const checkDollOverNavbar = () => {
  const doll = getVisibleDoll()

  if (!doll) {
    isSplit.value = false
    return
  }

  const rect = doll.getBoundingClientRect()
  const navbarHeight = getNavbarHeight()

  const dollIsOverNavbar = rect.top < navbarHeight && rect.bottom > 0

  isSplit.value = dollIsOverNavbar
}

const handleScroll = () => {
  if (!ticking) {
    window.requestAnimationFrame(() => {
      checkDollOverNavbar()
      ticking = false
    })

    ticking = true
  }
}

onMounted(() => {
  checkDollOverNavbar()

  window.addEventListener('scroll', handleScroll, { passive: true })
  window.addEventListener('resize', checkDollOverNavbar)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
  window.removeEventListener('resize', checkDollOverNavbar)
})
</script>

<template>
  <header class="nav-load-enter fixed inset-x-0 top-0 z-[12000]">
    <nav
      class="flex h-[70px] items-center justify-center bg-black/100 px-1 backdrop-blur-xl sm:h-[68px] sm:px-2 md:h-[76px] lg:px-4 xl:h-[86px] xl:px-6"
    >
      <div
        class="flex w-full max-w-[1500px] items-center justify-center transition-all duration-700 ease-[cubic-bezier(0.22,1,0.36,1)]"
      >
        <!-- Grupo izquierdo -->
        <div
          class="flex items-center justify-end gap-[0.20rem] transition-all duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] sm:gap-1 md:gap-2 lg:gap-3 xl:gap-4 2xl:gap-6"
          :class="isSplit ? '-translate-x-1 sm:-translate-x-2 md:-translate-x-4 xl:-translate-x-8' : 'translate-x-0'"
        >
          <template v-for="(item, index) in leftItems" :key="item.label">
            <a
              :href="item.href"
              class="nav-neon whitespace-nowrap text-[0.40rem] sm:text-[0.43rem] md:text-[0.52rem] lg:text-[0.58rem] xl:text-[0.62rem] 2xl:text-[0.72rem]"
            >
              {{ item.label }}
            </a>

            <img
              v-if="index !== leftItems.length - 1"
              src="/images/estrellas/estrellas 1.png"
              alt=""
              class="nav-separator-img"
            />
          </template>
        </div>

        <!-- Hueco central animado -->
        <div
          class="shrink-0 transition-all duration-700 ease-[cubic-bezier(0.22,1,0.36,1)]"
          :class="
            isSplit
              ? 'w-[9px] opacity-100 sm:w-[105px] md:w-[150px] lg:w-[220px] xl:w-[330px] 2xl:w-[420px]'
              : 'w-[14px] opacity-100 sm:w-[22px] md:w-[35px] lg:w-[45px] xl:w-[55px] 2xl:w-[75px]'
          "
        ></div>

        <!-- Grupo derecho -->
        <div
          class="flex items-center justify-start gap-[0.18rem] transition-all duration-700 ease-[cubic-bezier(0.22,1,0.36,1)] sm:gap-1 md:gap-2 lg:gap-3 xl:gap-4 2xl:gap-6"
          :class="isSplit ? 'translate-x-1 sm:translate-x-2 md:translate-x-4 xl:translate-x-8' : 'translate-x-0'"
        >
          <template v-for="(item, index) in rightItems" :key="item.label">
            <a
              :href="item.href"
              class="nav-neon whitespace-nowrap text-[0.40rem] sm:text-[0.43rem] md:text-[0.52rem] lg:text-[0.58rem] xl:text-[0.62rem] 2xl:text-[0.72rem]"
            >
              {{ item.label }}
            </a>

           <img
              v-if="index !== rightItems.length - 1"
              src="/images/estrellas/estrellas 1.png"
              alt=""
              class="nav-separator-img"
            />
          </template>
        </div>
      </div>
    </nav>
  </header>
</template>