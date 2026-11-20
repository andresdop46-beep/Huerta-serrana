# 05. Informe de Verificación, Bitácora de IA y Reflexión Final

## 1. Matriz de Verificación Técnica y Funcional (V01–V15)
| ID | Prueba realizada | Resultado | Estado |
|---|---|---|---|
| V01 | Navegación entre las 4 páginas en escritorio y móvil | Enlaces operativos y página activa marcada con ria-current="page" | PASS |
| V02 | Validación semántica HTML5 en las 4 vistas | Estructura con <header>, <nav>, <main>, <section>, <article> y <footer> | PASS |
| V03 | Carga de ilustraciones SVG en GitHub Pages | Rutas relativas en minúsculas y dimensiones explícitas verificadas | PASS |
| V04 | Responsividad en viewport móvil (360x800) | Sin desbordamiento horizontal; rejillas colapsan a 1 columna | PASS |
| V05 | Responsividad en viewport escritorio (1440x900) | Rejillas de 3 y 4 columnas alineadas correctamente | PASS |
| V06 | Contraste de colores en modo claro (WCAG AA) | Todos los pares texto/fondo superan el ratio 4.5:1 | PASS |
| V07 | Contraste de colores en modo oscuro (prefers-color-scheme: dark) | Corregido contraste en tablas y campos .formulario__campo | PASS |
| V08 | Navegación por teclado (Tab y Enter) | Enlace .skip-link operativo y contorno :focus-visible visible | PASS |
| V09 | Validación de formulario sin JavaScript | Impide envío con campos vacíos, email inválido o sin check RGPD | PASS |
| V10 | Funcionamiento de acordeones FAQ en contacto.html | Apertura y cierre nativo mediante <details>/<summary> | PASS |
| V11 | Impresión limpia de catálogo y tabla (Ctrl + P) | Oculta navegación y botones gracias a @media print | PASS |
| V12 | Rendimiento y ausencia de dependencias externas | Cero peticiones a fuentes o librerías de terceros | PASS |
| V13 | Compatibilidad de nombres de archivo en servidor Linux | Todos los archivos en minúsculas y codificación UTF-8 sin BOM | PASS |
| V14 | Historial de control de versiones en Git | Mínimo de 15 commits atómicos y descriptivos en rama main | PASS |
| V15 | Despliegue público y etiquetado de versión | Publicado en GitHub Pages con etiqueta 1.0 | PASS |

## 2. Bitácora de Uso de IA y Registro de Bugs Corregidos
Durante el desarrollo se empleó asistencia de IA para acelerar la generación de estructuras HTML5/CSS y diagnosticar incidencias de despliegue, realizando intervención manual crítica sobre los siguientes defectos detectados:
1. **Contraste de campos de formulario en modo oscuro:** El código CSS inicial asignaba ackground-color: var(--color-blanco) a .formulario__campo mientras color: var(--color-texto) cambiaba a blanco en modo oscuro, dejando texto blanco sobre fondo blanco. *Corrección:* Sustitución por ackground-color: var(--color-fondo).
2. **Contraste en filas alternas de tabla en modo oscuro:** Las celdas heredaban fondos claros con tipografía clara. *Corrección:* Ajuste mediante variables semánticas de superficie y borde en css/components.css.
3. **Visibilidad del menú <details> en escritorio:** Al ocultar <summary> por CSS sin incluir el atributo open en el HTML, el menú quedaba colapsado e inaccesible en index.html y productores.html. *Corrección:* Inclusión explícita del atributo open en <details class="navegacion__menu" open> en las 4 vistas.
4. **Rutas y sensibilidad a mayúsculas en GitHub Pages:** Las ilustraciones SVG no cargaban en producción por nombres no sincronizados y codificación de caracteres tras edición por terminal. *Corrección:* Normalización de nombres en minúsculas (img/portada-huerta.svg, img/sierra-norte.svg) y guardado en UTF-8 sin BOM.
5. **Espaciado entre botón principal e imagen en portada:** El botón .boton quedaba pegado al borde superior de la ilustración SVG. *Corrección:* Adición de margin-bottom: var(--space-lg) y reglas globales de márgenes en img.

## 3. Reflexión Final
El desarrollo de **Huerta Serrana** demuestra que es posible construir un sitio web comercial completo, accesible y visualmente sólido utilizando únicamente HTML5 semántico y CSS moderno sin depender de frameworks ni JavaScript. El mayor aprendizaje técnico del proyecto ha sido comprobar la importancia de validar manualmente el código asistido por IA en escenarios reales de producción (modo oscuro del sistema operativo, servidores Linux sensibles a mayúsculas en GitHub Pages y navegación por teclado), así como mantener una disciplina constante de commits atómicos en Git.