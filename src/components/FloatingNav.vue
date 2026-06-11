<script setup>
import { nextTick, onBeforeUnmount, onMounted, ref } from 'vue'

const isSplit = ref(true)

const navWrapperRef = ref(null)
const navContentRef = ref(null)
const navScale = ref(1)

let ticking = false
let resizeObserver = null
let contentObserver = null

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
  const dolls = Array.from(
    document.querySelectorAll('[data-doll-over-nav="true"]')
  )

  return dolls.find((doll) => doll.getClientRects().length > 0)
}

const getNavbarHeight = () => {
  if (window.innerWidth < 640) return 70
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

  isSplit.value = rect.top < navbarHeight && rect.bottom > 0
}

const updateNavScale = async () => {
  await nextTick()

  window.requestAnimationFrame(() => {
    const wrapper = navWrapperRef.value
    const content = navContentRef.value

    if (!wrapper || !content) return

    const availableWidth = wrapper.getBoundingClientRect().width
    const contentWidth = content.scrollWidth

    if (!availableWidth || !contentWidth) return

    navScale.value = Math.min(1, (availableWidth - 4) / contentWidth)
  })
}

const updateNavbar = async () => {
  checkDollOverNavbar()
  await updateNavScale()
}

const handleScroll = () => {
  if (!ticking) {
    window.requestAnimationFrame(() => {
      updateNavbar()
      ticking = false
    })

    ticking = true
  }
}

const handleResize = () => {
  updateNavbar()
}

onMounted(() => {
  updateNavbar()

  window.addEventListener('scroll', handleScroll, { passive: true })
  window.addEventListener('resize', handleResize)

  if (window.visualViewport) {
    window.visualViewport.addEventListener('resize', handleResize)
  }

  if (navWrapperRef.value) {
    resizeObserver = new ResizeObserver(updateNavbar)
    resizeObserver.observe(navWrapperRef.value)
  }

  if (navContentRef.value) {
    contentObserver = new ResizeObserver(updateNavbar)
    contentObserver.observe(navContentRef.value)
  }

  setTimeout(updateNavbar, 100)
  setTimeout(updateNavbar, 400)
  setTimeout(updateNavbar, 1000)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
  window.removeEventListener('resize', handleResize)

  if (window.visualViewport) {
    window.visualViewport.removeEventListener('resize', handleResize)
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
  <header class="fixed inset-x-0 top-0 z-[12000]">
    <nav
      class="flex h-[70px] items-center justify-center overflow-hidden bg-black px-1 backdrop-blur-xl sm:h-[68px] sm:px-2 md:h-[76px] lg:px-4 xl:h-[86px] xl:px-6"
    >
      <div
        ref="navWrapperRef"
        class="flex h-full w-full max-w-[1500px] items-center justify-center overflow-hidden"
      >
        <div
          ref="navContentRef"
          class="flex min-w-max origin-center items-center justify-center"
          :style="{ transform: `scale(${navScale})` }"
        >
          <!-- Grupo izquierdo -->
          <div
            class="flex items-center justify-end gap-[0.20rem] sm:gap-1 md:gap-2 lg:gap-3 xl:gap-4 2xl:gap-6"
            :class="
              isSplit
                ? '-translate-x-1 sm:-translate-x-2 md:-translate-x-4 xl:-translate-x-8'
                : 'translate-x-0'
            "
          >
            <template v-for="(item, index) in leftItems" :key="item.label">
              <a
                :href="item.href"
                class="nav-neon whitespace-nowrap text-[0.40rem] sm:text-[0.43rem] md:text-[0.52rem] lg:text-[0.58rem] xl:text-[0.62rem] 2xl:text-[0.72rem]"
                :class="item.label === 'El evento' ? '!font-black' : '!font-semibold'"
              >
                {{ item.label }}
              </a>

              <img
                v-if="index === 0"
                src="/images/estrellas/estrellas 3.png"
                alt=""
                class="nav-separator-img"
                @load="updateNavScale"
              />

              <img
                v-if="index === 1"
                src="/images/estrellas/estrellas 4.png"
                alt=""
                class="nav-separator-img"
                @load="updateNavScale"
              />
            </template>
          </div>

          <!-- Hueco central con estrella -->
          <div
            class="flex shrink-0 items-center justify-center"
            :class="
              isSplit
                ? 'w-[35px] opacity-100 sm:w-[105px] md:w-[150px] lg:w-[220px] xl:w-[330px] 2xl:w-[420px]'
                : 'w-[18px] opacity-100 sm:w-[22px] md:w-[35px] lg:w-[45px] xl:w-[55px] 2xl:w-[75px]'
            "
          >
            <img
              src="/images/estrellas/estrellas 2.png"
              alt=""
              class="nav-center-star"
              @load="updateNavScale"
            />
          </div>

          <!-- Grupo derecho -->
          <div
            class="flex items-center justify-start gap-[0.18rem] sm:gap-1 md:gap-2 lg:gap-3 xl:gap-4 2xl:gap-6"
            :class="
              isSplit
                ? 'translate-x-1 sm:translate-x-2 md:translate-x-4 xl:translate-x-8'
                : 'translate-x-0'
            "
          >
            <template v-for="(item, index) in rightItems" :key="item.label">
              <a
                :href="item.href"
                class="nav-neon whitespace-nowrap text-[0.40rem] sm:text-[0.43rem] md:text-[0.52rem] lg:text-[0.58rem] xl:text-[0.62rem] 2xl:text-[0.72rem]"
                :class="item.label === 'El evento' ? '!font-black' : '!font-semibold'"
              >
                {{ item.label }}
              </a>

              <img
                v-if="index === 0"
                src="/images/estrellas/estrellas 1.png"
                alt=""
                class="nav-separator-img"
                @load="updateNavScale"
              />

              <img
                v-if="index === 1"
                src="/images/estrellas/estrellas 2.png"
                alt=""
                class="nav-separator-img"
                @load="updateNavScale"
              />

              <img
                v-if="index === 2"
                src="/images/estrellas/estrellas 2.png"
                alt=""
                class="nav-separator-img"
                @load="updateNavScale"
              />
            </template>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>