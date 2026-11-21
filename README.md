# Analizador de Instagram (100% local y privado)

Aplicación web minimalista en un único archivo (`index.html`) hecha únicamente con **HTML, CSS y JavaScript puro (vanilla)** para analizar la exportación oficial de datos de Instagram sin subir nada a internet, sin pedir contraseñas y sin dependencias externas.

## Cómo usarla

1. Descarga o clona este repositorio y abre `index.html` con doble clic en cualquier navegador moderno (Chrome, Edge, Firefox o Safari).
2. Puedes probarla al instante de dos formas:
   - Pulsando el botón **«Probar con datos de ejemplo»** dentro de la propia web.
   - O arrastrando el archivo de prueba incluido [`datos_ejemplo_instagram.zip`](./datos_ejemplo_instagram.zip).
3. Para analizar tu propia cuenta:
   - Ve al [Centro de cuentas de Meta](https://accountscenter.instagram.com/info_and_permissions/) → **Exportar tu información** → **Crear exportación** → **Exportar al dispositivo**.
   - Selecciona tu cuenta de Instagram, elige **Desde el principio** como intervalo de fechas y cambia el formato a **JSON** (también funciona con HTML como respaldo).
   - Cuando recibas el `.zip`, arrástralo directamente sobre la página (también admite la carpeta descomprimida o archivos `.json` / `.html` sueltos).

## Qué incluye

- **Análisis principal:** quién no te sigue de vuelta, a quién no sigues tú, seguidores mutuos, totales, ratio seguidores/seguidos y tasa de reciprocidad.
- **Análisis adicionales:** solicitudes enviadas pendientes y recibidas, cuentas que dejaste de seguir recientemente, mejores amigos, bloqueados, restringidos, cronología por años y rango en días, cuentas con más likes y comentarios dados, chats con más mensajes, búsquedas recientes y tabla de diagnóstico de archivos leídos.
- **Privacidad y rendimiento:** lectura nativa de `.zip` en el navegador (Central Directory + `DecompressionStream('deflate-raw')`) que ignora fotos y vídeos pesados para no saturar la memoria RAM.
- **Compatibilidad de formatos:** soporta exportaciones JSON desde 2020 hasta 2026 (`connections.json` legado, `string_list_data`, variante `title` + `/_u/`, `label_values` + `fbid`), respaldo HTML con `DOMParser`, decodificación del mojibake UTF-8 de Meta (`Ã©` → `é`) y filtrado automático de carpetas `threads/`.
- **Utilidades:** modo claro/oscuro, buscador, orden alfabético o por fecha, enlace directo a cada perfil y exportación a CSV compatible con Excel (UTF-8 con BOM).

## Contenido del repositorio

- `index.html` — Aplicación completa en un solo archivo.
- `datos_ejemplo_instagram.zip` — Exportación ficticia realista para probar la carga de `.zip`.
- `README.md` — Esta guía rápida.
