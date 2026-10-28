# Patitas Felices · Maqueta web

Maqueta web estática de la fundación **Patitas Felices** (rescate, cuidado y adopción de animales), hecha solo con **HTML y CSS**, sin JavaScript. El diseño se hizo primero en Figma (wireframes en la carpeta `wireframes/`) y luego se pasó a código.

## Páginas

| Página | Archivo | Qué tiene |
|---|---|---|
| Inicio | `index.html` | Banner, carrusel de fotos, labor, testimonios, misión y visión, galería |
| Adopta | `views/adopta.html` | Filtros visuales y catálogo de 8 animales |
| Perfil | `views/perfil.html` | Tarjeta del animal elegido, historia, salud, hogar ideal y 3 sugerencias |
| Donaciones | `views/donaciones.html` | Banner, tres bloques informativos y formulario de donación simulado |
| Contacto | `views/contacto.html` | Formulario con validación visual, datos de contacto y redes |

## Cómo ejecutarlo

1. Abrir la carpeta `patitas-felices` en Visual Studio Code.
2. Instalar la extensión **Live Server**.
3. Clic derecho en `index.html` → **Open with Live Server**.

(También se puede abrir `index.html` con doble clic en el navegador.)

## Estructura

```
patitas-felices/
├── index.html
├── views/         adopta.html, perfil.html, donaciones.html, contacto.html
├── css/           variables.css, style.css, iconos.css, home.css, adopta.css, perfil.css, donaciones.css, contacto.css
├── storage/
│   ├── img/       imágenes
│   └── icons/     iconos .svg
├── wireframes/    diseño de Figma (1440 px)
└── README.md
```

## Diseño responsive

Se diseñó primero para celular y se fue agregando con `min-width`:

- **600 px**: celulares grandes (el catálogo pasa a 2 columnas)
- **768 px**: tablet (el menú hamburguesa se convierte en menú en fila; banner, misión/visión y perfil pasan a fila)
- **1024 px**: computador (el catálogo pasa a 4 columnas y el formulario queda al lado de los datos)

## Componentes simulados con CSS

- **Carrusel**: 3 fotos que se desplazan solas hacia la izquierda cada 3 segundos con `@keyframes` y `transform: translateX`.
- **Menú hamburguesa**: un `checkbox` escondido + el selector `:checked` (se abre y se cierra sin JavaScript).
- **Iconos**: archivos `.svg` usados como `background-image` desde `css/iconos.css` (clases `.icono` e `.icono-huella`, `.icono-casa`, etc.).
- **Perfil del animal**: cada "Ver perfil" del catálogo abre `perfil.html#nombre`, y `:target` muestra solo la tarjeta de ese animal.
- **Filtros**: 4 `select` con estilos (solo visuales, no filtran).
- **Validación del formulario**: `:placeholder-shown`, `:valid` e `:invalid`, y las clases `.error` y `.success` en un bloque de ejemplo.
- **Footer** con Flexbox y **catálogo/galería** con Grid.

## Imágenes

Las imágenes de `storage/img/` son provisionales. Para usar las del diseño, exportarlas desde Figma (Export → JPG) y guardarlas con el mismo nombre.

## Capturas de pantalla

*(Agregar aquí las capturas de Inicio, Adopta, Perfil y Contacto)*

## Página de donaciones

`views/donaciones.html` invita a la comunidad a ayudar a la fundación. Tiene un banner con el título «Ayúdanos a cambiar vidas», tres bloques informativos (¿Por qué donar?, ¿Cómo usamos las donaciones?, ¿Qué logra tu aporte?) y un formulario de donación **simulado** (nombre, correo, monto, método de donación y botón «Donar ahora»). No procesa pagos ni envía datos.

**Cómo verla:** abrir el proyecto con Live Server y entrar por la opción **Donaciones** del menú, o abrir `views/donaciones.html` directamente en el navegador. Sus estilos están en `css/donaciones.css` y su imagen en `storage/img/donaciones-banner.jpg`.

## Notas

- Los animales, historias, testimonios y datos de contacto son ficticios.
- Los botones "Solicitar adopción", "Enviar mensaje" y "Donar ahora" no envían nada.
