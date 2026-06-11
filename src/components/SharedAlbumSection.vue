<template>
  <section
    id="tu-huella"
    class="relative flex w-full items-center justify-center overflow-hidden bg-black"
  >
    <div
  class="album-frame relative grid w-full max-w-[1200px] grid-cols-2 overflow-hidden bg-[#ff8a35]"
>
  <!-- Línea neón central -->
  <img
    src="/images/iconos-decorar/LINEA.png"
    alt=""
    class="pointer-events-none absolute left-[52%] top-[-12%] z-10 h-[125%] w-[545px] -translate-x-1/2 object-contain drop-shadow-[0_0_14px_#ff4fd8] min-[390px]:w-[500px] sm:w-[190px] md:w-[230px] lg:w-[260px] xl:w-[300px]"
  />

  <!-- LADO IZQUIERDO: ÁLBUM -->
  <div
    class="relative flex min-h-[230px] flex-col items-center overflow-hidden px-[6%] py-[4%] text-center md:min-h-[300px] xl:min-h-[360px]"
  >
    <!-- Cámara neón -->
    <img
      src="/images/iconos-decorar/camara.png"
      alt="Cámara"
      class="absolute left-[6%] top-[6%] z-[4] h-auto w-[58px] rotate-[-8deg] object-contain min-[390px]:w-[48px] sm:w-[95px] md:w-[125px] lg:w-[155px] xl:w-[185px]"
    />

    <!-- Título -->
    <div
      class="album-title-block -translate-x-[10px] min-[390px]:-translate-x-[12px] sm:-translate-x-[10px] md:-translate-x-[8px] lg:-translate-x-[6px]"
    >
      <h2 class="album-title-3d">ALBUM DE</h2>
      <h2 class="album-title-3d">FOTOS</h2>
      <h2 class="album-title-3d">COMPARTIDO</h2>
    </div>

    <!-- Texto -->
    <p class="album-description text-[#be34b0] -translate-x-[10px] min-[390px]:-translate-x-[1px] sm:-translate-x-[10px] md:-translate-x-[8px] lg:-translate-x-[6px] ">
      BUSCO FOTÓGRAFOS POR UNA NOCHE<br />
      CAPTURA LOS MEJORES MOMENTOS DE MIS XV AÑOS<br />
      Y COMPÁRTELOS AQUÍ.
    </p>

    <a
      href="https://photos.app.goo.gl/MDtJZjWgwu9V2Do69"
      class="relative z-[5] mt-[6%] inline-flex h-[42px] w-[95px] translate-y-[10px] items-center justify-center rounded-full border-[3px] border-[#ff38c7] bg-[#f7d1ff] text-center font-['Montserrat'] text-[0.55rem] font-black uppercase leading-none tracking-[0.03em] text-[#ff38c7] no-underline shadow-[3px_3px_0_#901293,0_0_8px_#ffffff,0_0_16px_#ff38c7] transition hover:scale-105 hover:brightness-110 sm:h-[48px] sm:w-[120px] sm:text-[0.68rem] md:h-[55px] md:w-[150px] md:text-[0.8rem] lg:h-[62px] lg:w-[170px] lg:text-[0.95rem]"
    >
      VER ÁLBUM
    </a>

    <!-- Frase inferior -->
    <p
      class="album-bottom-text translate-x-[-3px] translate-y-[26px] min-[390px]:translate-y-[22px] sm:translate-y-[20px] md:translate-y-[18px] lg:translate-y-[16px]"
    >
      ¡QUIERO VER MI FIESTA A TRAVÉS DE TUS OJOS!
    </p>
  </div>

  <!-- LADO DERECHO: PLAYLIST -->
  <div
    class="relative flex min-h-[230px] flex-col items-center overflow-hidden px-[6%] py-[4%] text-center md:min-h-[300px] xl:min-h-[360px]"
  >
    <!-- Nota decorativa -->
    <img
      src="/images/evento/nota.png"
      alt=""
      class="absolute right-[-7%] top-[-6%] z-[3] w-[90px] object-contain min-[390px]:w-[100px] sm:w-[115px] md:w-[130px] lg:w-[145px]"
    />

    <!-- Título Playlist -->
    <h2
      class="playlist-title-3d translate-x-[4px] translate-y-[10px] min-[390px]:translate-x-[3px] sm:translate-x-[2px] md:translate-x-0"
    >
      PLAYLIST
    </h2>

    <!-- Texto -->
    <p
      class="playlist-description translate-x-[4px] translate-y-[-18px] text-[#c1ff72] min-[390px]:translate-x-[3px] min-[390px]:translate-y-[-17px] sm:translate-x-[2px] sm:translate-y-[-14px] md:translate-x-0 md:translate-y-[-12px]"
    >
      ¡SÉ PARTE DE LA BANDA SONORA DE MI FIESTA!<br />
      ESCANEA EL CÓDIGO Y AGREGA UNA CANCIÓN QUE<br />
      NO PUEDE FALTAR ESTA NOCHE.
    </p>

    <!-- Botón playlist -->
    <a
      href="https://open.spotify.com/playlist/51cLMnniHdUgTulRJzfeOu?si=eCeTIeOmRlC-OYvadsHYgA&pt=2030eac3ffc745dcf5a501cf3312036f"
      class="relative z-[5] mt-[6%] inline-flex h-[42px] w-[95px] translate-x-[2px] translate-y-[-6px] items-center justify-center rounded-full border-[3px] border-[#0b7d27] bg-[#c1ff72] text-center font-['Gagalin Regular'] text-[0.55rem] font-black uppercase leading-none tracking-[0.03em] text-[#0b7d27] no-underline shadow-[3px_3px_0_#0b7d27,0_0_8px_#c1ff72,0_0_16px_#29b554] transition hover:scale-105 hover:brightness-110 min-[390px]:translate-y-[-5px] sm:h-[48px] sm:w-[120px] sm:text-[0.68rem] md:h-[55px] md:w-[150px] md:translate-x-0 md:text-[0.8rem] lg:h-[62px] lg:w-[170px] lg:text-[0.95rem]"
    >
      ABRIR PLAYLIST
    </a>
  </div>
</div>
  </section>
</template>