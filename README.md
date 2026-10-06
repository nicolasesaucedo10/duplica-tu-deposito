# Landing “Duplicamos tu carga”

Versión estática lista para GitHub y Vercel. No necesita instalar dependencias ni ejecutar una compilación.

## Seguimiento del botón de WhatsApp

El botón apunta a `/chat/bplay`. Vercel reescribe esa ruta hacia el tracker
publicado en Railway y el script de `index.html` conserva automáticamente
`fbclid`, `utm_source`, `utm_campaign` y cualquier otro parámetro recibido.

No reemplazarlo por un enlace directo a `wa.me`: hacerlo saltearía el tracker
y la compra perdería la relación con el anuncio.

### Estado del destino (6 de octubre de 2026)

El destino configurado en `vercel.json`,
`https://meta-whatsapp-tracker-production.up.railway.app`, devuelve HTTP 404
con `Application not found`, tanto en `/health` como al abrir `/chat/bplay`
desde la landing. El enlace y la conservación de parámetros funcionan;
la redirección a WhatsApp queda pendiente de recuperar el servicio o configurar
la URL vigente del tracker. No se publicó un número alternativo ni se salteó
el seguimiento con un enlace directo.

## Condiciones mostradas

La oferta muestra un 100% extra en la primera carga de jugadores nuevos
mayores de 18 años, con una bonificación máxima de $8.000. El tope también
aparece en los metadatos y en el detalle desplegable, con ejemplos de carga.
El extra deja de crecer al alcanzar $8.000.

No se establecen una fecha de vencimiento, un mínimo de carga ni requisitos
de uso o retiro del beneficio que no hayan sido confirmados. La página indica
que deben consultarse antes de cargar.

## Configuración en Vercel

- Framework Preset: `Other`
- Build Command: dejar vacío
- Output Directory: dejar vacío o usar `.`
- Install Command: dejar vacío

Después elegí **Deploy**.
