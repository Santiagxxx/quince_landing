<template>
  <section
    id="cata"
    class="relative min-h-[118svh] w-full overflow-hidden bg-black text-white"
  >
    <!-- Luces decorativas de fondo -->
    <div class="pointer-events-none absolute inset-0">
      <div
        class="absolute left-[5%] top-[10%] h-20 w-20 rounded-full bg-fuchsia-500/20 blur-3xl sm:h-28 sm:w-28"
      ></div>

      <div
        class="absolute right-[12%] top-[18%] h-24 w-24 rounded-full bg-cyan-400/20 blur-3xl sm:h-32 sm:w-32"
      ></div>

      <div
        class="absolute bottom-[10%] left-[40%] h-28 w-28 rounded-full bg-lime-300/10 blur-3xl sm:h-40 sm:w-40"
      ></div>
    </div>

    <!-- Iconos neon decorativos -->
    <span
      class="neon-pink absolute left-[12%] top-[8%] text-4xl text-fuchsia-400 sm:left-[35%] sm:text-5xl lg:left-[40%] lg:text-6xl"
    >
      ☆
    </span>

    <span
      class="neon-pink absolute left-[6%] top-[34%] text-5xl text-fuchsia-400 sm:left-[28%] sm:text-7xl md:left-[32%] lg:left-[36%] lg:top-[33%] lg:translate-x-20 lg:-translate-y-10 lg:text-9xl"
    >
      ♡
    </span>

    <span
      class="neon-pink absolute right-[8%] top-[9%] text-4xl text-fuchsia-400 sm:text-5xl"
    >
      ♪
    </span>

    <span
      class="neon-cyan absolute left-[68%] top-[18%] text-3xl text-cyan-300 sm:left-[62%] sm:top-[15%] sm:text-4xl"
    >
      ˚
    </span>

    <span
      class="neon-cyan absolute bottom-[8%] right-[10%] hidden text-5xl text-cyan-300 md:block lg:right-[55%] lg:-translate-y-13 lg:text-7xl"
    >
      𝄞
    </span>

    <!-- Contenido principal -->
    <div
      class="relative z-10 mx-auto grid min-h-[115svh] max-w-[1440px] grid-cols-1 items-center gap-2 px-5 pb-20 pt-16 sm:px-8 md:grid-cols-[42%_58%] md:gap-0 md:px-10 md:py-10 lg:-translate-y-10 lg:px-16"
    >
      <!-- Texto izquierdo -->
      <div class="order-2 text-center md:order-1 md:text-left">
        <h1
          class="neon-pink translate-y-[15px] mb-4 font-jonathan text-[3.6rem] leading-[0.8] text-white sm:text-[4.8rem] md:mb-6 md:text-[5.3rem] lg:text-[6.3rem] xl:text-[7rem]"
        >
          Hola, soy Cata.
        </h1>

        <div
          class="mx-auto max-w-[520px] space-y-3 md:mx-0 md:space-y-4 lg:translate-y-6 lg:space-y-8"
        >
          <p class="text-[0.78rem] translate-y-[30px] font-medium leading-[1.25] text-[#ff0099] sm:text-[0.85rem] md:text-[0.9rem] lg:text-[1rem]">
            Hace quince años comenzó una historia llena de sueños, aprendizajes y momentos que han dejado huellas en mi corazón.
            No todos los caminos han sido fáciles, pero cada experiencia me ha enseñado a ser más fuerte, a valorar lo que tengo
            y a sonreír incluso en los días más difíciles.
          </p>

          <p class="text-[0.78rem] translate-y-[30px] font-medium leading-[1.25] text-[#ff0099] sm:text-[0.85rem] md:text-[0.9rem] lg:text-[1rem]">
            Hoy miro hacia atrás y veo a la niña que fui, tomada de la mano de las personas que me han amado, cuidado y acompañado
            en cada paso. Y mientras miro hacia adelante, siento emoción por todo lo que está por venir, por los sueños que aún quiero
            cumplir y por la persona en la que me estoy convirtiendo.
          </p>

          <p class="text-[0.78rem] translate-y-[30px] font-medium leading-[1.25] text-[#ff0099] sm:text-[0.85rem] md:text-[0.9rem] lg:text-[1rem]">
            Esta noche brillarán las luces, pero ninguna brillará más que la felicidad de compartir este momento con ustedes.
          </p>
        </div>
      </div>

      <!-- Imagen derecha -->
      <div
        class="order-1 relative flex min-h-[260px] items-center justify-center md:order-2 md:min-h-[620px] lg:min-h-screen"
      >
        <img
          src="/images/pastel.png"
          alt="Cata con torta de quince años"
          class="relative z-10 h-auto w-full max-w-[310px] object-contain drop-shadow-[0_0_35px_rgba(255,0,180,0.45)] sm:max-w-[430px] md:max-w-[620px] md:translate-y-10 lg:max-w-[760px] lg:translate-y-20"
        />
      </div>
    </div>

    <!-- Frase inferior -->
    <div
      class="pointer-events-none absolute bottom-5 translate-y-[10px] left-1/2 z-20 w-full -translate-x-1/2 px-5 text-center md:left-[24%] md:w-auto md:translate-x-0 md:text-left lg:bottom-8"
    >
      <p
        class="neon-green font-jonathan translate-y-[-12px] text-[2.3rem] leading-none text-lime-200 sm:text-[3.2rem] md:text-[4rem] lg:text-[4.6rem] xl:text-[5rem]"
      >
        “Una noche para brillar juntos”
      </p>
    </div>
  </section>
</template>