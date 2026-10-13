# ROTUL — sitio estático para GitHub Pages

El ZIP contiene la versión completa de ROTUL: Inicio, Catálogo, Proyectos, Servicios, Nosotros, Contacto y las 22 fichas de producto. No necesita instalación, compilación, Node.js ni un servidor de aplicaciones.

## Publicar

1. Descomprime el ZIP en tu computadora.
2. Sube **el contenido descomprimido** al repositorio de GitHub. `index.html`, `style.css`, `script.js`, `.nojekyll`, las carpetas de páginas y `assets/` deben quedar juntos en la raíz del repositorio. No subas únicamente el ZIP ni dejes todos los archivos dentro de una carpeta adicional.
3. En el repositorio, abre **Settings → Pages**. En **Build and deployment**, elige **Deploy from a branch**.
4. Selecciona la rama que contiene los archivos, normalmente **main**, y la carpeta **/(root)**. Guarda los cambios.
5. Espera a que GitHub termine la publicación y abre la dirección que muestra Pages. No es necesario escribir esa dirección en el código.

Guía oficial: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Archivos principales

- `index.html`: página de Inicio.
- `style.css`: todos los estilos, puntos de adaptación y fuentes locales.
- `script.js`: datos de contacto y productos, menú móvil, filtros, cotizaciones, carruseles, videos y parallax.
- `catalogo/index.html`: catálogo y buscador.
- `catalogo/<producto>/index.html`: una ficha por producto, con nombres de carpeta en minúsculas.
- `proyectos/index.html`, `servicios/index.html`, `nosotros/index.html` y `contacto/index.html`: páginas interiores.
- `assets/`: imágenes, videos y tipografías.
- `imagenes.md`: tabla de nombres y ubicación exacta de cada imagen y video.
- `.nojekyll`: archivo vacío que indica que se publican directamente los archivos estáticos. Si tu explorador oculta los archivos que empiezan con punto, actívalos para incluirlo.

## Rutas y funcionamiento

El Inicio carga `style.css` y `script.js`. Las páginas interiores usan `../style.css` y `../script.js`; las fichas de producto usan `../../`. Las imágenes también utilizan rutas relativas. Así funciona tanto en el dominio principal como en una subcarpeta de GitHub Pages.

No hay recursos, redirecciones ni enlaces de navegación que dependan del alojamiento anterior. Todos los nombres de archivo están en minúsculas y sin espacios.

Las únicas direcciones externas son acciones que necesariamente salen del sitio: WhatsApp, redes sociales y enlaces de atribución de fotografías. Ningún CSS, JavaScript, fuente, fotografía o video se carga desde otro servidor.

## Editar contenido y contacto

Los textos visibles se editan en el HTML de cada página. El menú y el footer están presentes en cada archivo HTML: si los cambias, repite el cambio en las demás páginas.

Al principio de `script.js`, en `window.ROTUL.site.contact`, puedes editar WhatsApp, teléfono, correo, dirección y redes. WhatsApp está configurado con **528993097065**. Conserva solo dígitos en ese campo, incluyendo el código de país.

El formulario prepara un mensaje con el producto o proyecto y los datos del visitante. El visitante revisa el mensaje y pulsa **Enviar por WhatsApp**. El sitio no almacena solicitudes ni envía correos desde un servidor.

Los iconos de Facebook e Instagram conservan el enlace de Facebook que proporcionaste para ambos. Para asignar un perfil de Instagram distinto, cambia su enlace en los footer de los HTML y en `window.ROTUL.site.contact.social`.

Los datos de producto están al principio de `script.js`. Si agregas o cambias un producto, actualiza también su tarjeta en `catalogo/index.html` y su ficha de detalle. Los códigos y nombres proporcionados se conservaron; no se muestran precios.

## Diseño y medios

Cada página incluye `meta viewport`. El CSS utiliza Grid, Flexbox, tamaños fluidos y puntos de adaptación para móvil, tableta y escritorio. Conserva la barra blanca, identidad roja/negra, catálogo, carruseles y videos.

Las imágenes y videos ya están incluidos. Consulta `imagenes.md` antes de reemplazarlos. Conserva las etiquetas que distinguen imágenes conceptuales y fotografías del catálogo.

Puedes abrir `index.html` en tu computadora para revisar navegación y contenido. Para comprobar el comportamiento final, revisa también la URL publicada por GitHub en tu móvil y computadora. Las restricciones de reproducción automática dependen del navegador; hay portadas y controles manuales de respaldo.

## Verificación de esta entrega

Se comprobaron rutas internas y recursos bajo una subcarpeta de prueba, nombres de archivo, sintaxis de JavaScript y funciones principales mediante pruebas automatizadas. No fue posible realizar una revisión visual en navegadores o dispositivos reales desde este entorno.
