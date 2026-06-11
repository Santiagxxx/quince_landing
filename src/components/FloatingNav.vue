<script setup>
import { computed, nextTick, onBeforeUnmount, onMounted, ref } from 'vue'

const navWrapperRef = ref(null)
const navContentRef = ref(null)
const navScale = ref(1)

let resizeObserver = null
let contentObserver = null

const navItems = [
  {
    label: 'Inicio',
    href: '#inicio',
    starAfter: '/images/estrellas/estrellas 4.png',
  },
  {
    label: 'Cata',
    href: '#cata',
    starAfter: '/images/estrellas/estrellas 3.png',
  },
  {
    label: 'Evento',
    href: '#evento',
    starAfter: '/images/estrellas/estrellas 4.png',
  },
  {
    label: 'Dress-code',
    href: '#dress-code',
    starAfter: '/images/estrellas/estrellas 2.png',
  },
  {
    label: 'Tu huella',
    href: '#tu-huella',
    starAfter: '/images/estrellas/estrellas 4.png',
  },
  {
    label: 'Lluvia de sobres',
    href: '#lluvia-sobres',
    starAfter: '/images/estrellas/estrellas 1.png',
  },
  {
    label: 'Asiste',
    href: '#te-esperamos',
    starAfter: null,
  },
]

const starScale = computed(() => {
  const scale = navScale.value || 1
  return Math.min(2.8, Math.max(1.4, 1.75 / scale))
})

const updateNavScale = async () => {
  await nextTick()

  window.requestAnimationFrame(() => {
    const wrapper = navWrapperRef.value
    const content = navContentRef.value

    if (!wrapper || !content) return

    const availableWidth = wrapper.getBoundingClientRect().width
    const contentWidth = content.scrollWidth

    if (!availableWidth || !contentWidth) return

    navScale.value = Math.min(1, (availableWidth - 8) / contentWidth)
  })
}

onMounted(() => {
  updateNavScale()

  window.addEventListener('resize', updateNavScale)

  if (window.visualViewport) {
    window.visualViewport.addEventListener('resize', updateNavScale)
  }

  if (navWrapperRef.value) {
    resizeObserver = new ResizeObserver(updateNavScale)
    resizeObserver.observe(navWrapperRef.value)
  }

  if (navContentRef.value) {
    contentObserver = new ResizeObserver(updateNavScale)
    contentObserver.observe(navContentRef.value)
  }

  setTimeout(updateNavScale, 100)
  setTimeout(updateNavScale, 400)
  setTimeout(updateNavScale, 1000)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', updateNavScale)

  if (window.visualViewport) {
    window.visualViewport.removeEventListener('resize', updateNavScale)
  }

  if (resizeObserver) {
    resizeObserver.disconnect()
  }

  if (contentObserver) {
    contentObserver.disconnect()
  }
})
</script>

<template>
  <header class="nav-load-enter fixed inset-x-0 top-0 z-[12000]">
    <nav
      class="flex h-[70px] items-center justify-center overflow-hidden bg-black px-1 backdrop-blur-xl sm:h-[68px] sm:px-2 md:h-[76px] lg:px-4 xl:h-[86px] xl:px-6"
    >
      <div
        ref="navWrapperRef"
        class="flex h-full w-full max-w-[1500px] items-center justify-center overflow-hidden"
      >
        <div
          ref="navContentRef"
          class="nav-content-fit flex min-w-max origin-center items-center justify-center"
          :style="{
            transform: `scale(${navScale})`,
            '--star-scale': starScale,
          }"
        >
          <template v-for="item in navItems" :key="item.label">
            <a :href="item.href" class="nav-neon">
              {{ item.label }}
            </a>

            <img
              v-if="item.starAfter"
              :src="item.starAfter"
              alt=""
              class="nav-separator-img"
              @load="updateNavScale"
            />
          </template>
        </div>
      </div>
    </nav>
  </header>
</template>