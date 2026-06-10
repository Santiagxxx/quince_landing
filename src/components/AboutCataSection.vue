<script setup>
const textoCata = [
  `Hace quince años comenzó una historia llena de sueños, aprendizajes y momentos que han dejado huellas en mi corazón. No todos los caminos han sido fáciles, pero cada experiencia me ha enseñado a ser más fuerte, a valorar lo que tengo y a sonreír incluso en los días más difíciles.`,

  `Hoy miro hacia atrás y veo a la niña que fui, tomada de la mano de las personas que me han amado, cuidado y acompañado en cada paso. Y mientras miro hacia adelante, siento emoción por todo lo que está por venir, por los sueños que aún quiero cumplir y por la persona en la que me estoy convirtiendo.`,

  `Mis quince años no son solo una celebración. Son un agradecimiento a la vida, a mi familia, a mis amigos y a cada persona que ha sido parte de mi historia. Gracias por estar aquí, por creer en mí y por ayudarme a llenar mi vida de recuerdos hermosos.`,

  `Esta noche brillarán las luces, pero ninguna brillará más que la felicidad de compartir este momento con ustedes.`
]
</script>

<template>
  <section
    id="cata"
    class="relative min-h-screen w-full overflow-hidden bg-black text-white"
  >
    <!-- Luces decorativas de fondo -->
    <div class="pointer-events-none absolute inset-0">
      <div class="absolute left-[8%] top-[12%] h-28 w-28 rounded-full bg-fuchsia-500/20 blur-3xl"></div>
      <div class="absolute right-[20%] top-[22%] h-32 w-32 rounded-full bg-cyan-400/20 blur-3xl"></div>
      <div class="absolute bottom-[14%] left-[42%] h-40 w-40 rounded-full bg-lime-300/10 blur-3xl"></div>
    </div>

    <!-- Iconos neon decorativos -->
    <span class="neon-icon absolute left-[40%] top-[10%] text-6xl text-fuchsia-400">
      ☆
    </span>

    <span class="neon-icon absolute left-[36%] top-[33%] text-5xl text-fuchsia-400">
      ♡
    </span>

    <span class="neon-icon absolute right-[6%] top-[8%] text-5xl text-fuchsia-400">
      ♪
    </span>

    <span class="neon-icon-cyan absolute left-[62%] top-[15%] text-4xl text-cyan-300">
      ˚
    </span>

    <span class="neon-icon-cyan absolute bottom-[9%] left-[40%] text-7xl text-cyan-300">
      𝄞
    </span>

    <!-- Contenido principal -->
    <div
      class="relative z-10 mx-auto grid min-h-screen max-w-[1440px] grid-cols-1 items-center px-5 py-10 md:grid-cols-[42%_58%] md:px-10 lg:px-16"
    >
      <!-- Texto izquierdo -->
      <div class="order-2 md:order-1">
        <h1
          class="neon-pink mb-8 font-jonathan text-[4.2rem] leading-none text-white sm:text-[5.5rem] md:text-[6rem] lg:text-[7rem]"
        >
          hola, soy Cata.
        </h1>

        <div class="max-w-[520px] space-y-5">
          <p
            v-for="(parrafo, index) in textoCata"
            :key="index"
            class="text-[1rem] font-medium leading-[1.25] text-fuchsia-500 sm:text-[1.08rem] md:text-[1.05rem] lg:text-[1.15rem]"
          >
            {{ parrafo }}
          </p>
        </div>
      </div>

      <!-- Imagen derecha -->
      <div
        class="order-1 relative flex min-h-[430px] items-center justify-center md:order-2 md:min-h-screen"
      >
        <!-- 
          Cambia esta ruta por tu imagen real.
          Ejemplo:
          public/images/cata-torta.png
        -->
        <img
          src="/images/pastel.png"
          alt="Cata con torta de quince años"
          class="relative z-10 h-auto w-full max-w-[760px] object-contain drop-shadow-[0_0_35px_rgba(255,0,180,0.45)]"
        />


      </div>
    </div>

    <!-- Frase inferior -->
    <div
      class="pointer-events-none absolute bottom-5 left-1/2 z-20 w-full -translate-x-1/2 px-5 text-center"
    >
      <p
        class="neon-green font-['Sacramento',cursive] text-[2.5rem] leading-none text-lime-200 sm:text-[3.5rem] md:text-[4.5rem] lg:text-[5rem]"
      >
        “Una noche para brillar juntos”
      </p>
    </div>
  </section>
</template>
