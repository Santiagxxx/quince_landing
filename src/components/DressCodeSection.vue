<script setup>
const dressIdeas = [
  "/images/referencias/foto1.jpg",
  "/images/referencias/foto2.jpg",
  "/images/referencias/foto3.jpg",
  "/images/referencias/foto4.jpg",
  "/images/referencias/foto5.jpg",
  "/images/referencias/foto6.jpg",
];
</script>

<template>
  <section id="dress-code" class="dress-artboard-wrap bg-black">
    <div class="dress-artboard-scale">
      <div
        class="relative h-[620px] w-[1000px] overflow-hidden bg-black text-white"
      >
        <!-- Decoraciones -->
        <span
          class="absolute left-[25px] top-[182px] z-[1] text-[44px] leading-none text-[#ff7df0] [text-shadow:0_0_8px_#ff00bf,0_0_22px_#ff00bf]"
        >
          <img
            src="/images/iconos-decorar/iconos-right.png"
            alt="El dress code"
            class="w-[80px] max-w-none"
          />
        </span>

        <!-- Texto principal -->
        <div class="absolute left-[34px] top-[56px] z-[5] w-[420px]">
          <div class="dress-title-wrap " aria-label="EL DRESS CODE">
            <!-- Línea 1 -->
            <h2 class="dress-title-3d dress-title-dress">
              <span class="dress-layer-extrude">EL DRESS</span>
              <span class="dress-layer-front">EL DRESS</span>
            </h2>

            <!-- Línea 2 -->
            <h2 class="dress-title-3d dress-title-code">
              <span class="dress-layer-extrude">CODE</span>
              <span class="dress-layer-front">CODE</span>
            </h2>
          </div>
          <div
            class="mt-[40px] w-[380px] font-medium text-[15px] uppercase leading-[1.16] tracking-[0.03em] text-pink-200"
          >
            <p>Brilla con color</p>
            <p>
              Te invitamos a usar colores vibrantes, neón o detalles
              fluorescentes.
            </p>
            <p>¡Esta noche no hay espacio para pasar desapercibido!</p>

            <p
              class="dress-reserved-neon mt-[12px] inline-block text-[1em] font-black leading-none"
            >
              Nos reservamos el uso del color lila
            </p>
          </div>
        </div>

        <!-- Cata principal -->
        <div
          class="pointer-events-none absolute right-[-40px] top-[70px] z-[4]"
        >
          <img
            src="/images/chicle.png"
            alt="Cata dress code"
            class="h-[405px] w-auto max-w-none object-contain drop-shadow-[0_0_32px_rgba(255,0,190,0.58)]"
          />
        </div>

        <!-- Tira de iconos neón derecha -->
        <div
          class="pointer-events-none absolute right-[0px] top-[3px] z-[3] w-[150px] rotate-340 opacity-95"
        >
          <img
            src="/images/iconos-decorar/cata-dress.jpeg"
            alt="Iconos neón dress code"
            class="h-[550px] w-full max-w-none object-contain"
          />
        </div>
        <div
          class="pointer-events-none absolute left-[420px] top-[50px] z-[3] w-[150px] rotate-15 opacity-95"
        >
          <img
            src="/images/iconos-decorar/ultima-cara-dress.jpeg"
            alt="Iconos neón dress code"
            class="h-[300px] w-full max-w-none object-contain"
          />
        </div>
        <!-- Título ideas -->
        <div
          class="absolute bottom-[56px] left-[34px] z-[5] text-[22px] font-semibold uppercase leading-[1.18] tracking-[0.06em] text-[#f7d6ff]"
        >
          Aquí te dejamos<br />
          algunas ideas:
        </div>

        <!-- Ideas -->
        <div
          class="absolute bottom-[5px] left-[320px] right-0 z-[5] grid h-[140px] grid-cols-6"
        >
          <div
            v-for="(idea, index) in dressIdeas"
            :key="index"
            class="overflow-hidden border-l-2 border-black bg-[#111]"
          >
            <img
              :src="idea"
              alt="Idea de dress code"
              class="h-full w-full object-cover"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
