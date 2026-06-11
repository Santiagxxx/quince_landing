<template>
  <section
    id="evento"
    class="relative flex w-full items-center justify-center overflow-hidden bg-black"
  >
    <div
      class="evento-frame relative grid w-full grid-cols-[61%_39%] overflow-hidden bg-[#d016f2] xl:max-w-[1200px] mx-auto"
    >
      <!-- LADO IZQUIERDO -->
      <div
        class="evento-left relative overflow-hidden bg-[#ce23ff] px-[10.5%] py-[4.5%]"
      >
        <!-- Títulos EL y EVENTO separados -->
        <div class="flex w-full flex-row items-center justify-center gap-[0.70em]">
          <h2 class="evento-title-3d" aria-label="EL">
            <span class="evento-title-layer evento-layer-extrude">EL</span>
            <span class="evento-title-layer evento-layer-front">EL</span>
          </h2>

          <h2 class="evento-title-3d" aria-label="EVENTO">
            <span class="evento-title-layer evento-layer-extrude">EVENTO</span>
            <span class="evento-title-layer evento-layer-front">EVENTO</span>
          </h2>
        </div>

        <!-- Información del evento -->
        <div class="evento-info">
          <!-- Fecha -->
          <div class="evento-row">
            <img
              src="/images/evento/fecha.png"
              alt="Fecha"
              class=" translate-x- translate-y-[-15px] w-[px] sm:w-[38px] md:w-[45px] lg:w-[55px] xl:w-[65px] h-auto object-contain"
            />

            <div>
              <p class="evento-main-text translate-y-[-15px]">DOMINGO</p>
              <p class="evento-main-text translate-y-[-15px]">19 DE JULIO 2026</p>
            </div>
          </div>

          <!-- Ubicación -->
          <div class="evento-row">
            <img
              src="/images/evento/ubi.png"
              alt="Ubicación"
              class="translate-y-[-15px] w-[38px] sm:w-[45px] md:w-[52px] lg:w-[62px] xl:w-[72px] h-auto object-contain"
            />

            <div>
              <p class="evento-main-text translate-y-[-15px]">CALLE 145 # 46 - 80</p>
              <p class="evento-main-text translate-y-[-15px]">ED LUGANO, SALON SOCIAL</p>
            </div>
          </div>

          <!-- Hora -->
          <div class="evento-row">
            <img
              src="/images/evento/reloj.png"
              alt="Hora"
              class="translate-y-[-15px] w-[70px] sm:w-[60px] md:w-[52px] lg:w-[62px] xl:w-[72px] h-auto object-contain"
            />

            <div>
              <p class="evento-main-text translate-y-[-15px]">5:30 P.M.</p>
            </div>
          </div>
        </div>

        <!-- Imagen decorativa de notas / figuras grande -->
        <img
          src="/images/evento/nota.png"
          alt=""
          class="absolute z-[4] right-[-1%] bottom-[2%] w-[90px] sm:w-[120px] md:w-[160px] lg:w-[190px] xl:w-[220px] h-auto object-contain"
        />

        <!-- Segunda nota musical más pequeña -->
        <img
          src="/images/evento/nota.png"
          alt=""
          class="absolute z-[6] right-[1%] translate-y-[25px] top-[15%] w-[60px] sm:w-[70px] md:w-[90px] lg:w-[105px] xl:w-[120px] h-auto rotate-[10deg] object-contain"
        />
      </div>

      <!-- LADO DERECHO -->
      <div class="evento-timeline-box">
        <img
          src="/images/evento/timeline.png"
          alt="Timeline del evento"
          class="evento-timeline-img"
        />
      </div>
    </div>
  </section>
</template>