# EL POAIG — Estado del Proyecto

> Actualizado: 27 mayo 2026

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

## 🆕 Actualización 26-05 — Specs del 26 de mayo (versión EN)

Aplicados en `index-v2.html`. Pendiente replicar en versiones ES y JP.

### 1. Sustituciones exactas de copy ✅ Completado
- `What between 1,000 and 3,000 years old produce` → `What trees between 1,000 and 3,000 years old produce`
- `350mg/kg` → `350 mg/kg`
- `olieras this season` → `Porcelain oliera this season` (todas las instancias)
- `Mechanical milking technique` → `Gentle mechanical harvesting`
- `Beaten at ambient temperature` → `Milled at low temperature`
- `low injection rates` → `low extraction yield`
- `Continental climate` → `Mediterranean climate`
- `Where others extract 20%, we yield 11-14%` → `While the industry may pursue yields around 20%, we accept only 11-14% to preserve integrity.`

### 2. Botón de compra ✅ Completado
- Cambiado texto de 3 botones `"PURCHASE"` → `"Acquire your numbered oliera"` (Hero, Producto, CTA final)
- Eliminado `--olive-green` de `:root` y reemplazadas todas las instancias por `var(--gold)`

### 3. Eliminar color verde oliva ✅ Completado
- Variable `--olive-green: #6B7B3A` eliminada del `:root`
- 11 instancias reemplazadas por `var(--gold)`:
  - `.press-card:hover .press-line`
  - `.philosophy-text h2 em`
  - `.origin-text h2 em`
  - `.process-header .section-label` y `::before/::after`
  - `.process-bottling-callout .callout-label`
  - SVG topo backgrounds (philosophy y origin)
  - SVG olive-divider en process
- **Nota:** `--olive-dark` (#3A3A2A) se mantiene — es color diferente para fondos intermedios.

### 4. Icono rojo Adobe
- **Estado:** ❌ No aplica — No encontrado en el proyecto.

### 5. Redirección por defecto
- **Estado:** ❌ No aplica — No encontrado en el proyecto.

### 6. Bloque de certificaciones ✅ Completado
- Nueva sección `.section-certifications` insertada entre section-cta y footer-branch
- 4 ítems con inline SVGs: Certified organic agriculture · Millenary olive tree origin · Polyphenol analysis · Numbered porcelain oliera
- Diseño: grid 4 columnas desktop, 2x2 mobile, fondo charcoal, iconos y texto en gold/cream

### 7. Claim principal reforzado en hero ✅ Completado
- Subheading añadido como `<span class="hero-subheading">` en hero-tagline (label gold, 9px uppercase):
  *"High-polyphenol organic EVOO from certified millenary olive trees."*
- Claim principal sustituyó al texto anterior en `<p>` del hero-tagline:
  *"The world's first organic EVOO from certified millenary Farga olive trees. More than 300 mg/kg of polyphenols. A rare oil that contributes to the protection of blood lipids from oxidative stress."*
- Bug residual corregido: `var(--olive-green)` en `.process-header .section-label::before/::after` (línea 1066) sustituido por `var(--gold)`

---

## 🆕 Actualización 27-05 — Diseño y layout (versión EN)

Aplicados en `index-v2.html`. Pendiente replicar en versiones ES y JP.

### 1. Certifications section rediseñada ✅ Completado
- Header añadido: label "Certifications & Distinctions" + h2 "Recognised by the highest standards"
- Animación scroll reveal en header y cada cert-item (stagger con delay-1 a delay-4)
- Iconos aumentados de 32px a 48px para legibilidad de detalles SVG
- Opacidad subida: img 0.8→0.85, span 0.7→0.8
- Hover states: translateY(-4px) + opacity full en img y span
- Separadores verticales gold entre items (desktop) y horizontales en grid 2×2 (mobile)
- `max-width: 140px` en span para evitar wraps desiguales

### 2. Hero mobile: layout corregido ✅ Completado
- Colisión entre h1 title y hero-bottom content en móvil resuelta
- Título posicionado arriba del bottom content con `margin-bottom: 30px`
- `.hero` cambia a `flex-direction: column` + `justify-content: flex-end` en mobile
- `.hero-bottom` cambia a `position: relative` (sale de absolute, entra en flujo flex)
- Padding hero: `90px 24px 24px` (espacio para navbar + respiración)
- Badge compactado (`padding: 14px 20px`, `badge-value font-size: 22px`)
- Subheading y párrafo compactados (`font-size 8px/9px`, `letter-spacing 3px`)
- `min-height: 100svh` (sin el piso de 700px)

### 3. Eliminado --olive-dark por completo ✅ Completado
- Variable `--olive-dark: #3A3A2A` eliminada de `:root`
- 9 instancias reemplazadas con variables existentes:
  - Textos secundarios sobre warm-white → `var(--charcoal)` (6 instancias)
  - Hover press-card → `var(--cream)` (1 instancia)
  - Product img-frame background → `var(--charcoal)` (1 instancia)
  - Section CTA background → `var(--charcoal)` (1 instancia)
- `.section-cta` ahora tiene `border-top` y `border-bottom` gold sutil (mismo patrón que `section-dacosta`)

### 4. Precio removido de la CTA section ✅ Completado
- Elemento `.cta-price` con `€265` eliminado de la sección CTA
- El CTA ahora solo contiene: label, h2, p descriptivo y botón "Acquire your numbered oliera"

---

## 🔄 En progreso / Pendiente

### Replicar cambios de copy en ES y JP
- Los cambios de las Actualizaciones 25-05 y 26-05 se aplicaron únicamente en `index-v2.html` (versión EN).
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
| Sustituciones exactas 26-05 (8 cambios) | ✅ Completado |
| Botón "Acquire your numbered oliera" | ✅ Completado |
| Eliminar verde oliva (olive-green) | ✅ Completado |
| Icono rojo Adobe | ❌ No aplica |
| Redirección por defecto EN | ❌ No aplica |
| Bloque certificaciones | ✅ Completado |
| Claim principal hero reforzado | ✅ Completado |
| Certifications rediseñada | ✅ Completado |
| Hero mobile layout corregido | ✅ Completado |
| --olive-dark eliminado | ✅ Completado |
| Precio removido de CTA | ✅ Completado |