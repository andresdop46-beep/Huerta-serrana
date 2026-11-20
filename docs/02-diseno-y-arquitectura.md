# 02. Diseño Visual, Sistema de Tokens y Decisiones Técnicas

## 1. Estrategia Mobile-First y Maquetación
El CSS se ha estructurado de forma modular en cuatro hojas de estilo cargadas en cascada:
1. css/tokens.css: Definición centralizada de *Custom Properties* (colores, escala tipográfica fluida, espaciados en em y radios de borde).
2. css/base.css: Normalización de estilos, tipografía del sistema de alto rendimiento sin peticiones externas, soporte automático para modo oscuro (@media (prefers-color-scheme: dark)), foco visible (:focus-visible) y respeto a la preferencia de movimiento reducido (prefers-reduced-motion).
3. css/layout.css: Contenedores centrados, cabecera adaptable, menú desplegable sin JavaScript mediante <details> y rejillas responsivas con grid-template-columns: repeat(auto-fit, minmax(..., 1fr)).
4. css/components.css: Estilos de componentes aislados y hoja de impresión (@media print).

## 2. Metodología BEM
Para evitar colisiones de especificidad y facilitar el mantenimiento, todas las clases siguen la convención **Bloque__Elemento--Modificador**:
- .cabecera, .cabecera__contenedor, .cabecera__logo
- .navegacion, .navegacion__menu, .navegacion__lista, .navegacion__enlace
- .tarjeta, .tarjeta__titulo, .tarjeta__precio, .tarjeta--destacada
- .formulario, .formulario__grupo, .formulario__grupo--check, .formulario__campo

## 3. Decisiones Técnicas Relevantes
- **Cero JavaScript:** Toda la interactividad (menú móvil, preguntas frecuentes y validación de formulario) se resuelve con HTML5 semántico nativo (<details>, <summary>, restricciones de <input>), eliminando bloqueos de renderizado y garantizando compatibilidad total.
- **Gráficos vectoriales SVG:** Las ilustraciones (img/portada-huerta.svg y img/sierra-norte.svg) se han diseñado en SVG puro (< 1 KB cada una) con dimensiones explícitas (width y height) para evitar desplazamientos de diseño (*Cumulative Layout Shift* = 0).