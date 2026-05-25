# EL POAIG — Estado del Proyecto

> Actualizado: 25 mayo 2026

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

## 🆕 Actualización 25-05 — Cambios de copy y nuevas secciones (versión EN)

Aplicados en `index-v2.html`. Pendiente replicar en versiones ES y JP.

### 1. Precio eliminado del botón de compra
- Se quitó la mención de `€265` de todos los CTAs de la página (Hero, sección de producto, sección final).
- Los botones quedan como `PURCHASE` limpio, sin precio visible.

### 2. Rango de edad de los olivos corregido
- Sustituidas todas las menciones absolutas a "3,000 years" o similares por el rango correcto: **"between 1,000 and 3,000 years old"**.
- Afecta al texto del Hero, la sección de Filosofía, la descripción del producto y la etiqueta del contador dinámico (ahora dice *"Years of History (Aged 1,000 to 3,000)"*).

### 3. Eliminado el término "Millennial"
- Reemplazado en todas sus apariciones por **"Millenary Farga Olive Trees"** o **"Millenary EVOO"** según el contexto.
- Afecta al title de la página, el loader de carga, el logotipo en la barra de navegación, el menú móvil, el distintivo del Hero y los textos del marquee rotativo.

### 4. Contexto de temporada añadido al número 615
- Donde aparecía solo el número `615`, ahora se acompaña de: **"615 olieras this season (production varies each harvest, October to October)"**.
- Afecta al contador de unidades, la etiqueta del producto, la tabla de especificaciones técnicas y el CTA de cierre.

### 5. Eliminadas referencias a acidez; sustituidas por claims de antioxidantes
- Se retiró el bloque de texto sobre acidez (<0.2%) y se reemplazó por: *"First ORGANIC EVOO from millenary olive trees. 350mg/kg polyphenols. Early harvest high polyphenol olive oil. Premium antioxidant EVOO."*
- En la tabla técnica del producto, el campo "Acidity" se reemplazó por **"Polyphenols: 350 mg/kg"**.

### 6. Nuevo claim: embotellado bajo demanda
- Añadido un bloque destacado al final de la sección de procesos con el texto: *"This oil is never pre-bottled. It stays protected from oxidation in stainless steel tanks without oxygen until the moment you order. Bottled on demand. Never before."*

### 7. Claims de Joaquim incorporados
- Añadido el párrafo de storytelling de marca en la sección del producto: *"El Poaig was not born to make oil. It was born to protect a landscape, a territory..."*
- Se presenta como texto narrativo de peso, sin atribución de nombre propio.

### 8. Nueva sección destacada: Quique Dacosta
- Creada una sección independiente de alto impacto visual entre el video cinemático y los contadores.
- Diseño inspirado en marcas de vino de Borgoña: cita en tipografía serif cursiva a gran escala, nombre del chef en Playfair Display grande, subtítulo con restaurante y estrellas en tipografía monoespaciada dorada.
- Texto: *"El Mil del Poaig, on our table since the beginning."* — Quique Dacosta · 3 Michelin Stars.

---

## 🔄 En progreso / Pendiente

### Replicar cambios de copy en ES y JP
- Los 8 cambios de copy de la Actualización 25-05 se aplicaron únicamente en `index-v2.html` (versión EN).
- **Acción:** Traducir y aplicar los mismos cambios en `index-es.html` y `jp/index.html`.

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
| Logos en SVG | ✅ Verificado |
| Publicación en dominio | ✅ Verificado |
| Copy actualizado EN (8 puntos 25-05) | ✅ Completado |
| Copy actualizado ES y JP | 🔄 Pendiente |
