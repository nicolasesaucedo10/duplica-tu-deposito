# Landing “Duplicamos tu carga”

Versión estática lista para GitHub y Vercel. No necesita instalar dependencias ni ejecutar una compilación.

## Seguimiento del botón de WhatsApp

El botón apunta a `/chat/bplay`. Vercel reescribe esa ruta hacia el tracker
publicado en Railway y el script de `index.html` conserva automáticamente
`fbclid`, `utm_source`, `utm_campaign` y cualquier otro parámetro recibido.

No reemplazarlo por un enlace directo a `wa.me`: hacerlo saltearía el tracker
y la compra perdería la relación con el anuncio.

## Configuración en Vercel

- Framework Preset: `Other`
- Build Command: dejar vacío
- Output Directory: dejar vacío o usar `.`
- Install Command: dejar vacío

Después elegí **Deploy**.
