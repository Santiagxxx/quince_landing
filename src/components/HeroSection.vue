<template>
  <section
    id="inicio"
    class="relative min-h-[300px] overflow-visible bg-[#f2b2ef] pt-[82px] md:min-h-[700px] xl:pt-[86px]"
  >
    <!-- Fondo -->
    <div
      class="absolute inset-0 bg-[linear-gradient(90deg,#f7b9f2_0%,#f3a9ee_45%,#f7c1f5_100%)]"
    ></div>

    <!-- Brillos -->
    <div
      class="absolute left-[3%] top-[22%] h-36 w-36 rounded-full bg-white/25 blur-3xl sm:h-48 sm:w-48 md:left-[8%] md:top-[20%]"
    ></div>

    <div
      class="absolute right-[4%] top-[20%] h-40 w-40 rounded-full bg-white/20 blur-3xl sm:h-56 sm:w-56 md:right-[12%] md:top-[18%]"
    ></div>

    <div
      class="absolute left-1/2 top-[6%] h-56 w-56 -translate-x-1/2 rounded-full bg-fuchsia-400/20 blur-3xl md:top-0 md:h-64 md:w-64"
    ></div>

    <!-- Texto izquierdo: LOS -->
    <div
      class="hero-los-enter absolute left-[9%] top-[40%] z-30 sm:left-[10%] md:left-[20%] md:top-[30%]"
    >
      <p class="hero-script hero-los">
        Los
      </p>
    </div>

    <!-- Texto derecho: DE CATA -->
    <div
      class="hero-cata-enter absolute right-[5%] top-[50%] z-30 text-right sm:right-[8%] md:right-[15%] md:top-[27%]"
    >
      <p class="hero-script hero-de -translate-x-7 -translate-y-5">
        de
      </p>

      <p class="hero-script hero-cata">
        Cata
      </p>
    </div>

    <!-- Fecha -->
    <div
      class="hero-date-enter absolute bottom-[14px] left-1/6 z-40 w-full -translate-x-1/2 text-center  text-[#cb22ea] md:bottom-[8px] md:left-[16%] md:w-auto md:translate-x-0 md:text-left"
    >
      <p class="text-[7px] font-black -translate-x-2 tracking-[0.18em] sm:text-[13px]">
        19.07.2026
      </p>

      <p class="mt-2 text-[7px] font-black tracking-[0.16em] sm:text-[13px]">
        #CATALINDA15
      </p>
    </div>

    <!-- Imagen central encima del navbar - PC -->
      <div
        class="hero-doll-enter pointer-events-none absolute inset-x-0 top-[100px] bottom-0 z-[180] hidden items-end justify-center xl:flex"
      >
        <img
          id="hero-doll-over-nav"
          src="/images/cata15.png"
          alt="Cata con número 15"
          class="h-[calc(100%+86px)] w-auto max-w-none object-contain object-bottom"
        />
      </div>

      <!-- Imagen responsive tablet/celular -->
          <div
            class="hero-doll-enter pointer-events-none absolute inset-x-0 top-[-150px] bottom-60 z-[0] flex items-end justify-center xl:hidden"
          >
            <img
              data-doll-over-nav="true"
              src="/images/cata15.png"
              alt="Cata con número 15"
              class="h-[calc(90%+38px)] w-auto max-w-none translate-y-[240px]  translate-x-[-5%] object-contain object-bottom sm:h-[calc(100%+68px)] md:h-[calc(100%+76px)]"
            />
          </div>
  </section>
</template>