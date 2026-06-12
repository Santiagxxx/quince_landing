<template>
  <section
    id="te-esperamos"
    class="relative flex w-full items-center justify-center overflow-hidden bg-black"
  >
    <div
      class="relative aspect-[986/528] w-full max-w-[1200px] overflow-hidden"
    >
      <!-- Fondo completo -->
      <img
        src="/images/fondo.png"
        alt=""
        class="absolute inset-0 z-[1] h-full w-full object-cover"
      />

      <!-- Muñeca con flores -->
      <img
        src="/images/flores.png"
        alt="Cata con flores"
        class="absolute bottom-0 left-[-1%] z-[5] h-[104%] w-auto object-contain"
      />

      <!-- Texto -->
      <div
        class="absolute right-0 top-0 z-[6] flex h-full w-[48%] flex-col justify-start pl-[5%] pr-[4%] pt-[8%] text-left"
      >
        <p
          class="max-w-[520px] font-['Oswald'] text-[0.40rem] font-black uppercase leading-[1.25] tracking-[0.04em] text-[#c1ff72] min-[390px]:text-[0.46rem] sm:text-[0.65rem] md:text-[0.82rem] lg:text-[1rem] xl:text-[1.12rem]"
>
          "MI FIESTA NO ESTARÍA COMPLETA SIN TI. POR FAVOR CONFIRMA TU ASISTENCIA
          PARA COMPARTIR JUNTOS UNA NOCHE LLENA DE LUCES, MÚSICA Y MOMENTOS
          INOLVIDABLES."
        </p>

        <p
          class="mt-[8%] max-w-[520px] font-['Gagalin_Regular'] text-[0.44rem] font-black uppercase leading-[1.25] tracking-[0.04em] text-[#c1ff72] min-[390px]:text-[0.52rem] sm:text-[0.72rem] md:text-[0.9rem] lg:text-[1.05rem] xl:text-[1.15rem]"
        >
          POR FAVOR CONFIRMA TU ASISTENCIA ANTES DEL 01.07.2026
        </p>

        <a
          href="https://forms.gle/EArPnF8km5t6whSo7"
          target="_blank"
          rel="noopener noreferrer"
          class="mt-[6%] inline-flex w-fit items-center justify-center rounded-full border-[2px] border-[#c1ff72] bg-[#c1ff72] px-[14px] py-[7px] font-['Oswald'] text-[0.42rem] font-bold uppercase leading-none tracking-[0.08em] text-[#ff0094] no-underline transition duration-200 hover:scale-105 hover:bg-white hover:text-[#ff0094] min-[390px]:translate-x-[4px] translate-y-[17px] text-[0.48rem] sm:px-[18px] sm:py-[9px] sm:text-[0.65rem] md:px-[22px] md:py-[10px] md:text-[0.78rem] lg:px-[26px] lg:py-[12px] lg:text-[0.9rem] xl:text-[1rem]"
        >
          Confirma tu asistencia aqui
        </a>
      </div>
    </div>
  </section>
</template>