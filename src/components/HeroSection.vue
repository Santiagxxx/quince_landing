<template>
  <section
    id="inicio"
    class="relative h-[445px] overflow-visible bg-[#f2b2ef] md:h-[505px]"
  >
    <!-- Fondo -->
    <div
      class="absolute inset-0 bg-[linear-gradient(90deg,#f7b9f2_0%,#f3a9ee_45%,#f7c1f5_100%)]"
    ></div>

    <!-- Brillos -->
    <div
      class="absolute left-[8%] top-[20%] h-48 w-48 rounded-full bg-white/25 blur-3xl"
    ></div>
    <div
      class="absolute right-[12%] top-[18%] h-56 w-56 rounded-full bg-white/20 blur-3xl"
    ></div>
    <div
      class="absolute left-1/2 top-0 h-64 w-64 -translate-x-1/2 rounded-full bg-fuchsia-400/20 blur-3xl"
    ></div>
    <!-- Texto izquierdo -->
    <div class="absolute left-[16%] top-[23%] z-20">
      <p class="hero-script hero-los">Los</p>
    </div>

    <!-- Texto derecho -->
    <div class="absolute right-[12%] top-[15%] z-20 text-right">
      <p class="hero-script hero-de">de</p>
      <p class="hero-script hero-cata">Cata</p>
    </div>

    <!-- Fecha -->
    <div class="absolute bottom-[58px] left-[16%] z-20 text-[#b00094]">
      <p class="text-[13px] font-black tracking-[0.18em]">19.07.2026</p>
      <p class="mt-2 text-[13px] font-black tracking-[0.16em]">#CATALINA15</p>
    </div>

    <!-- Imagen central superpuesta al navbar -->
    <div
      class="pointer-events-none absolute inset-x-0 top-[-30px] bottom-0 z-[60] flex items-end justify-center"
    >
      <img
        src="/images/cata15.png"
        alt="Cata con número 15"
        class="h-[95%] w-auto max-w-none object-contain object-bottom md:h-[95%]"
      />
    </div>
  </section>
</template>
