# Especificaciones del Proyecto

## 1. Añadir la versión en español | [✅]
El contrato menciona explícitamente español, inglés y los idiomas que el cliente necesite. Ahora mismo solo existen **EN** y **JP**.

- **Acción:** Crear `index-es.html` siguiendo el mismo proceso de versionado: copia, edita, aplica en paralelo.
- **Copy:** El copy en español no es una traducción literal del inglés. El inglés usa posicionamiento identitario (*"You don't buy this oil, you're chosen"*). El español puede ser algo más narrativo y directo, con el mismo nivel de cuidado. 
- **Nota:** Consulta con Jose el copy antes de aplicarlo.

## 2. Integrar el botón de compra con Shopify | [✅]
Este es el entregable funcional más crítico. El botón de compra en la sección **Product** de la landing tiene que conectar directamente al checkout de Shopify existente, sin fricción y sin modificar la tienda.

- **URL del producto:** [https://www.elpoaig.com/products/el-mil-02-olive-oil](https://www.elpoaig.com/products/el-mil-02-olive-oil)
- **Implementación:** El acceso a Shopify ya está disponible (ver sección 6). Úsalo para conectar el botón directamente al checkout. 
- **Importante:** La web `elpoaig.com` es Shopify, **no WordPress**. No existe ningún WordPress en este proyecto.

## 3. QA completo en mobile | [✅]
El contrato promete optimización completa móvil. El draft funciona en mobile pero hay elementos que se ocultan por debajo de 900px sin haber pasado un QA exhaustivo:
- Cursor personalizado.
- Imágenes flotantes.
- Corner frames del producto.
- Texto de las citas del carousel de prensa.

Hay que revisar y corregir todo esto en una pantalla real o emulador.

## 4. Resolver el parpadeo del hero (opcional pero recomendado) - [✅] LISTO
El vídeo del hero usa un freeze en el último frame que puede parpadear un instante al cargarse desde caché en algunos navegadores.

- **Solución:** Añadir un `poster` estático `.jpg` como fallback en el elemento de vídeo. Es una mejora de calidad que vale la pena incluir antes de publicar.

## 5. Sustituir 4 logos de prensa a SVG | [❌]
Los logos de **TIME**, **The Times**, **Wallpaper*** y **El Mundo** son actualmente PNG ráster. 

- **Mejora:** Sus versiones SVG están disponibles en Wikimedia y darían máxima nitidez en cualquier pantalla. No es bloqueante pero suma calidad.

## 6. Publicar la landing en el dominio definitivo | [❌]
Una vez que la landing esté completa y haya pasado el QA final, hay que publicarla en `elpoaig.com`. 

> [!IMPORTANT]
> Consulta con Jose la decisión de dónde y cómo alojarla antes de empezar. Hay dos opciones muy distintas:

1. **Opción A:** Publicarla dentro de Shopify como página personalizada usando el editor de temas o un template Liquid.
2. **Opción B:** Alojarla en un hosting externo (Netlify, un bucket, etc.) apuntando el subdominio desde el DNS.

Son implementaciones completamente diferentes. No empieces este paso sin tener esa decisión confirmada.
