# 01. Especificación Funcional y Arquitectura - Huerta Serrana

## 1. Descripción del proyecto y público objetivo
**Huerta Serrana S. Coop.** es una plataforma web estática para una alianza de cuatro productores locales de la Sierra Norte de Madrid (Buitrago del Lozoya, Lozoyuela, El Atazar y Torrelaguna) orientada a la venta directa de hortalizas, miel, lácteos y panadería artesanal sin intermediarios.
- **URL pública en producción:** https://andresdop46-beep.github.io/Huerta-serrana/
- **Público objetivo:** Consumidores particulares y familias de la Comunidad de Madrid interesados en producto de proximidad, transparencia de origen y reparto semanal/quincenal.

## 2. Requisitos Funcionales (RF1–RF10)
- **RF1 (Navegación persistente y accesible):** Menú global en las 4 páginas sin dependencias de JavaScript (<details>/<summary>), con indicador de página activa (ria-current="page") y enlace de salto al contenido (.skip-link).
- **RF2 (Propuesta de valor en portada):** Presentación clara del modelo de venta directa en menos de 48 horas y acceso rápido al catálogo.
- **RF3 (Explicación del proceso en 3 pasos):** Flujo visual de selección, solicitud y entrega jueves/sábado.
- **RF4 (Modalidades de cestas y comparativa):** Tres planes mensuales (Básica, Familiar y Gourmet) y tabla comparativa accesible con atributos scope="col" y scope="row".
- **RF5 (Catálogo de temporada):** Listado de 12 productos con precio por unidad/kg, productor de origen y declaración explícita de alérgenos.
- **RF6 (Fichas de productores y territorio):** Información detallada de los 4 productores locales, ubicación en la Sierra Norte y mapa esquemático SVG.
- **RF7 (Formulario de solicitud de pedido):** Validación nativa HTML5 (equired, 	ype="email", 	ype="tel", pattern), etiquetas <label> vinculadas y consentimiento RGPD obligatorio.
- **RF8 (Preguntas frecuentes):** Acordeón nativo accesible mediante etiquetas <details> y <summary>.
- **RF9 (Diseño adaptable Mobile-First):** Maquetación fluida desde pantallas móviles (320px) hasta escritorio mediante CSS Grid y Flexbox.
- **RF10 (Accesibilidad WCAG AA y modo oscuro):** Contraste mínimo garantizado, soporte automático para prefers-color-scheme: dark, prefers-reduced-motion y hoja de estilos de impresión (@media print).

## 3. Arquitectura de información y paleta WCAG AA
- **Estructura de páginas:** index.html (Inicio), catalogo.html (Catálogo), productores.html (Productores) y contacto.html (Contacto y pedido).
- **Paleta cromática:**
  - Verde Bosque (#2F5D3A) sobre Blanco Hueso (#FAF6EC) — Ratio de contraste: **7.4:1 (AAA)**.
  - Texto Principal (#1F2A22) sobre Fondo (#FAF6EC) — Ratio de contraste: **13.8:1 (AAA)**.
  - Terracota (#B5532A) y Ocre Miel (#F2B134) como acentos semánticos y visuales.