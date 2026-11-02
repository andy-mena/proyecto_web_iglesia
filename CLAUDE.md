# Instrucciones del Proyecto: Sitio Web de Iglesia

## 1. Arquitectura y Stack Tecnológico
* Framework: Next.js App Router (directorio `/app`). Prohibido usar el antiguo directorio `/pages`.
* Renderizado: Prioriza Server Components. Usa la directiva `'use client'` únicamente cuando el componente necesite interactividad del usuario (ej. menú móvil, selector de idiomas).
* Estilos: Utiliza exclusivamente clases de Tailwind CSS. No crees archivos CSS personalizados ni módulos CSS.

## 2. Sistema de Diseño
* **OBLIGATORIO:** Antes de construir o modificar cualquier interfaz, debes leer el archivo `design.md` ubicado en la raíz. Extrae de ahí la paleta de colores, tipografías y reglas de espaciado.
* Enfoque UI/UX: Aplica diseño "mobile-first". Estructura los componentes primero para pantallas pequeñas y utiliza los prefijos `md:` y `lg:` de Tailwind para adaptar el diseño a tablets y computadoras de escritorio.

## 3. Requerimientos Funcionales Específicos
* **Soporte Bilingüe (i18n):** Estructura el directorio `/app` para manejar rutas por idioma (ej. `/app/[lang]`). Utiliza diccionarios locales (archivos JSON) para alternar los textos entre Español e Inglés sin bases de datos.
* **Optimización Fotográfica:** Utiliza siempre el componente `<Image>` de `next/image` para todas las fotografías. Asegúrate de configurar correctamente los atributos `alt` y los tamaños para garantizar carga rápida (lazy loading).
* **Módulo de Contacto:** Construye el formulario de contacto preparando la función de envío (submit) para interactuar con una API de terceros (ej. Formspree o Web3Forms). No escribas código de conexión a bases de datos propias.
* **Multimedia y Geolocalización:**
  - Videos y Mapas: Insértalos mediante `iframe` utilizando la clase de Tailwind `aspect-video` para mantener la proporción responsiva.
  - Documentos PDF: Crea botones de redirección usando etiquetas `<a>` con los atributos `href` (hacia Google Drive), `target="_blank"` y `rel="noopener noreferrer"`.