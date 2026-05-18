# EL POAIG — Estado del Proyecto

> Actualizado: 14 mayo 2026

---

## ✅ Completado

### Landing en español
- Página en español creada (`index-es.html` en raíz y `es/index.html`)
- Página en japonés organizada en `jp/index.html`
- Traducción completa de todos los textos (hero, navegación, secciones, opiniones, pie de página)
- Rutas de imágenes y videos corregidas para que funcionen desde subcarpetas (`/es/` y `/jp/`)
- Paridad estructural verificada: mismas clases, IDs y estructura que la versión en inglés

### Menú hamburguesa para móvil
- Botón de hamburguesa visible solo en pantallas menores a 900px
- Menú overlay de pantalla completa con fondo oscuro y tipografía clara
- Animación de entrada/deslizamiento suave
- Botón de cierre (X) funcional
- Cierre automático al tocar cualquier enlace del menú

### Video del hero sin parpadeo
- Eliminada la animación de zoom infinito que causaba temblor visual
- El video se reproduce una vez, se congela en el último frame y permanece completamente quieto
- Escala estática aplicada para mantener la estética cinematográfica

### Meta viewport optimizado
- Agregado `viewport-fit=cover` para pantallas con notch
- Altura del hero ajustada con `100svh` para evitar barras de navegación móvil
- Altura mínima del nav ajustada para móvil (70px)

### Documentación de diseño
- Creado `requirements/design.md` con el sistema de diseño completo (colores, tipografías, espaciado, componentes, animaciones)

---

## 🔄 En progreso / Pendiente

### Revisión de galería en móvil
- Las descripciones de las imágenes de la galería solo aparecen al pasar el cursor (hover). En pantallas táctiles no hay hover, por lo que el usuario nunca ve el título ni la descripción de cada imagen.
- **Acción:** Mostrar captions siempre visibles en móvil o agregar interacción táctil.

### Legibilidad del carrusel de prensa en móvil
- El carrusel de citas de medios se desplaza muy rápido para leer cómodamente en pantallas pequeñas.
- Las tarjetas son estrechas y el texto resulta pequeño.
- **Acción:** Reducir velocidad de animación y ajustar tamaño de tarjetas/texto en móvil.

### Áreas táctiles en móvil
- Algunos botones y enlaces en la versión móvil tienen áreas de toque menores al estándar recomendado (44px), lo que puede dificultar la interacción para usuarios con dedos gruesos o motricidad limitada.
- **Acción:** Aumentar padding y altura mínima de botones clave en móvil.

### Altura del hero en teléfonos pequeños
- En dispositivos con pantallas muy pequeñas (ej. iPhone SE), el hero puede extenderse más allá de la pantalla, empujando el contenido hacia abajo.
- **Acción:** Ajustar altura mínima del hero para pantallas compactas.

### Logos de prensa en formato SVG
- Los 14 logos de medios actualmente son imágenes PNG. Convertirlos a SVG mejoraría la nitidez en pantallas Retina y reduciría el peso de carga.
- **Acción:** Vectorizar logos principales o conseguir versiones SVG de los medios.

### Publicación en dominio
- Decisión pendiente sobre hosting: ¿publicar como página externa independiente o integrar dentro de Shopify?
- **Acción:** Definir estrategia de publicación y dominio.

---

## Resumen rápido

| Elemento | Estado |
|---|---|
| Landing en inglés | ✅ Lista |
| Landing en japonés | ✅ Lista |
| Landing en español | ✅ Lista |
| Menú hamburguesa móvil | ✅ Implementado |
| Video hero estable | ✅ Corregido |
| Botón de compra Shopify | ✅ Verificado |
| Galería táctil | 🔄 Pendiente |
| Carrusel de prensa móvil | 🔄 Pendiente |
| Áreas táctiles óptimas | 🔄 Pendiente |
| Logos en SVG | 🔄 Pendiente |
| Publicación en dominio | 🔄 Pendiente |

