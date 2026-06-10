# Landing Page - Los 15 de Cata

Landing page en Vue 3 + Vite para una invitación digital de 15 años.

## Secciones incluidas

- Inicio
- Cata
- El evento
- Dress-code
- Tu huella
- Lluvia de sobres
- Te esperamos

Las imágenes fueron extraídas del documento base enviado por el cliente y se usan como arte principal para respetar al máximo el diseño original.

## Ejecutar en local

```bash
npm install
npm run dev
```

Luego abre la URL que indique Vite, normalmente:

```txt
http://localhost:5173
```

## Compilar para producción

```bash
npm run build
```

Los archivos finales quedan en:

```txt
dist/
```

## Configurar envío del formulario

El formulario está listo para enviar las respuestas a un endpoint externo.

Opción rápida recomendada: Formspree.

1. Crear un formulario en Formspree.
2. Copiar el endpoint.
3. Crear un archivo `.env` en la raíz del proyecto.
4. Agregar:

```env
VITE_RSVP_ENDPOINT=https://formspree.io/f/xxxxxxx
```

5. Reiniciar el servidor de desarrollo:

```bash
npm run dev
```

Mientras no exista `VITE_RSVP_ENDPOINT`, el formulario funciona en modo demo y guarda una copia local en el navegador.

## Dónde cambiar las imágenes

Las imágenes están en:

```txt
public/images/
```

Puedes reemplazar cualquiera manteniendo el mismo nombre del archivo.

## Dónde cambiar los textos del formulario

El formulario está en:

```txt
src/components/RsvpForm.vue
```

## Dónde cambiar las secciones

El listado de secciones está en:

```txt
src/data/sections.js
```
