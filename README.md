# Analizador de Instagram (100 % local y privado)

🌐 **Abrir aplicación online (GitHub Pages):** **[https://alfonsodfernandez.github.io/igf/](https://alfonsodfernandez.github.io/igf/)**

Aplicación web minimalista en un único archivo (`index.html`) hecha únicamente con **HTML, CSS y JavaScript puro (vanilla)** para analizar la exportación oficial de datos de Instagram sin subir nada a internet, sin pedir contraseñas y sin dependencias externas.

> 🔒 **Privacidad real:** aunque la web esté alojada en GitHub Pages, **todo el análisis se ejecuta 100 % en local dentro de tu navegador**. Ningún archivo, usuario ni mensaje sale de tu dispositivo (funciona incluso sin conexión a internet).

## Cómo usarla

1. **Directamente online:** entra en [https://alfonsodfernandez.github.io/igf/](https://alfonsodfernandez.github.io/igf/) desde ordenador o móvil. Al abrirla verás de inmediato una vista previa interactiva con datos de ejemplo.
2. **En local (sin internet):** descarga o clona este repositorio y abre `index.html` con doble clic en cualquier navegador moderno (Chrome, Edge, Firefox o Safari).
3. **Analizar tu propia cuenta:**
   - Pulsa **«¿Cómo exportar en JSON?»** en la barra superior o ve al [Centro de cuentas de Meta](https://accountscenter.instagram.com/info_and_permissions/) → **Exportar tu información** → **Crear exportación** → **Exportar al dispositivo**.
   - Selecciona tu cuenta de Instagram, elige **Desde el principio** como intervalo de fechas y cambia el formato a **JSON** (también funciona con HTML como respaldo).
   - Cuando recibas el `.zip`, arrástralo sobre cualquier punto de la pantalla o pulsa **«Importar .zip»** (también admite carpeta descomprimida o archivos `.json` / `.html` sueltos).

## Qué incluye

- **Resumen visual compartible («Tu Año en Instagram» / Story Cards):** botón **Resumen visual** (o tecla `W`) que abre 5 tarjetas narrativas (*Tu círculo real*, *Tus conexiones más fieles*, *Tu ritmo en Instagram*, *Diagnóstico de limpieza* y *Resumen ejecutivo*) navegables con flechas o teclado (`←`/`→`) y descargables como PNG en alta resolución (`1080×1350` 4:5 Story o `1080×1080` 1:1 Post) renderizados en `<canvas>` nativo sin librerías externas.
- **Índice de Afinidad real (`0–100`):** puntuación transparente por cuenta que cruza reciprocidad, Mejores amigos, antigüedad, likes, comentarios y mensajes directos; visible en cada fila, en el Inspector lateral (con desglose de factores) y disponible para ordenar listas por **Mayor afinidad** o **Menor afinidad** (ideal para detectar cuentas fantasma).
- **Mapa de actividad (Heatmap estilo GitHub Contributions):** en la pestaña *Interacciones*, visualiza tu ritmo de actividad real (a partir de fechas de likes, comentarios y mensajes) con selector **Semana × Hora (7×24)** y **Último año (52 semanas)**, tooltip interactivo, día pico y franja horaria.
- **Modo privacidad en un clic:** oculta automáticamente todos los `@usuarios` y nombres en la interfaz y en las Story Cards PNG descargadas para compartir capturas con tranquilidad.
- **Análisis principal:** quién no te sigue de vuelta, a quién no sigues tú, seguidores mutuos, totales, ratio seguidores/seguidos, tasa de reciprocidad y evolución temporal interactiva (**Por año**, **Por mes** y **curva Acumulada** en SVG).
- **Comparador histórico entre dos exportaciones (Snapshot Diff):** carga una segunda exportación anterior desde *«Comparar con exportación anterior»* o la pestaña **Cambios (Diff)** para descubrir nuevos seguidores, **quién te dejó de seguir**, nuevos seguidos, cuentas que dejaste de seguir y **cambios de `@username`** detectados por `fbid` o fecha exacta, todo exportable a CSV.
- **Inspector de cuenta (ficha lateral):** haz clic sobre cualquier `@usuario` para abrir un panel lateral con toda su información cruzada: índice de afinidad con desglose, estados de relación, fechas exactas y diferencia en días, likes dados, comentarios (con vista previa de los últimos textos), mensajes directos encontrados y acciones rápidas (*Abrir en Instagram*, *Copiar `@usuario`*, *Marcar como revisado*).
- **Filtros combinados, lista de limpieza y atajos de teclado:**
  - Filtros rápidos por antigüedad y actividad (*Todos*, *Más de 1 año*, *Sin likes ni comentarios míos*, *Con interacción*, *Revisados*).
  - Selección múltiple persistida en `localStorage` para copiar los `@usuarios` al portapapeles o exportar solo tu selección a CSV compatible con Excel (UTF-8 con BOM).
  - Atajos de teclado: `/` enfoca el buscador, `1`–`7` cambia de pestaña, `W` abre el Resumen visual (`←`/`→` navega tarjetas) y `Esc` cierra modales o el inspector lateral.
- **Solicitudes, gestión e interacciones:** solicitudes enviadas pendientes y recibidas, dejados de seguir recientemente, mejores amigos, bloqueados, restringidos, rankings de likes/comentarios/chats, búsquedas recientes (`profile_searches.json`) y tabla de diagnóstico de archivos leídos.
- **Privacidad y compatibilidad:** lectura nativa de `.zip` en el navegador (Central Directory + `DecompressionStream('deflate-raw')`) que omite fotos y vídeos pesados para ahorrar RAM; soporta exportaciones JSON 2020–2026 (`connections.json`, `string_list_data`, variante `title` + `/_u/`, `label_values` + `fbid`), respaldo HTML con `DOMParser`, decodificación de mojibake UTF-8 de Meta (`Ã©` → `é`) y filtrado automático de carpetas `threads/`.

## Contenido del repositorio

- `index.html` — Aplicación completa en un solo archivo.
- `datos_ejemplo_instagram.zip` — Exportación ficticia realista para probar la carga real de `.zip`.
- `README.md` — Esta guía rápida.
