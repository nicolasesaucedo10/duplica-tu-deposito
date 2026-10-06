# Landing “Duplicamos tu carga”

Versión estática lista para GitHub y Vercel. No necesita instalar dependencias ni ejecutar una compilación.

## Seguimiento del botón de WhatsApp

El botón apunta a `/chat/bplay`. Vercel reescribe esa ruta hacia
`https://bplay-crm-nicolas-production.up.railway.app/chat/bplay`.
El script de `index.html` conserva `fbclid`, todos los parámetros UTM y
cualquier otro parámetro recibido. Las antiguas direcciones
`meta-whatsapp-tracker-production` y `panel-tracker-production` quedaron fuera de uso.

El servicio elige un soporte activo y conectado, registra el origen de la
visita y prepara un mensaje con una referencia `Ref: LP-...`. Cuando la persona
lo envía, esa referencia vincula el origen con su conversación en el CRM.
Si la persona elimina la referencia, no se vincula automáticamente.
Abrir el botón no envía un mensaje ni crea un destinatario de campañas.

Si no hay un soporte conectado, muestra un aviso temporal para volver a
intentar. `HEAD /chat/bplay` permite verificar el destino sin registrar clics.

No reemplazar el botón por un enlace directo a `wa.me`: saltearía el registro
local de origen. La atribución queda en el CRM; esta recuperación no incluye
el envío automático de compras a Meta mediante Conversions API.

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
