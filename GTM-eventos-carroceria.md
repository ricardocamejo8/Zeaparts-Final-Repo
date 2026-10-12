# Eventos de conversión — /carroceria

Todos los eventos se envían al `dataLayer` del contenedor existente **GTM-MKPZRV3S** con `page: "carroceria"`. Configura en GTM un trigger "Custom Event" por nombre y envíalo a GA4 / Google Ads.

## Conversiones primarias (marcar como conversión en Google Ads)

| Evento | gtm_label | Dónde |
|---|---|---|
| `whatsapp_click` | `carroceria-hero` | Botón principal hero |
| `whatsapp_click` | `carroceria-formulario` | Envío del formulario (también dispara `generate_lead`) |
| `whatsapp_click` | `carroceria-pieza` (+ `pieza`) | Click en tarjeta de pieza |
| `whatsapp_click` | `carroceria-modelo-{spark,aveo,sail}` | Tarjetas de modelo |
| `whatsapp_click` | `carroceria-cta-final` / `carroceria-fab` / `carroceria-sticky` / `carroceria-nav` | CTAs secundarios |
| `llamar_click` | `carroceria-hero` / `-nav` / `-cta-final` / `-sticky` / `-footer` | Todos los `tel:` |
| `generate_lead` | `carroceria-formulario` | Evento GA4 estándar, ideal como conversión principal |

## Micro-conversiones / engagement

- `landing_view` — carga de la página (útil para audiencias)
- `faq_open` — label = pregunta abierta
- `scroll_depth` — label = 25 / 50 / 75 / 100

## URLs para los anuncios (message match)

Anclas de sección (recomendadas para Quality Score — la URL final coincide con el modelo del anuncio y aterriza directo en «¿Qué pieza necesitas?»):

- `zeaparts.cl/carroceria#spark`
- `zeaparts.cl/carroceria#aveo`
- `zeaparts.cl/carroceria#sail`

El hash personaliza igual que el parámetro: H1, subtítulo, título de la pestaña, título de la sección de piezas, slide inicial, modelo pre-seleccionado y el `landing_view` sale como `carroceria-{modelo}`.

Alternativa con parámetro (mismo comportamiento, útil si el tracking de Ads recorta el hash):

- `zeaparts.cl/carroceria?modelo=spark` — alias `zeaparts.cl/carroceria-spark`
- `zeaparts.cl/carroceria?modelo=aveo` — alias `zeaparts.cl/carroceria-aveo`
- `zeaparts.cl/carroceria?modelo=sail` — alias `zeaparts.cl/carroceria-sail`

Sin parámetro muestra la versión genérica "Spark, Aveo y Sail".

## Recomendación GTM

1. Trigger: Custom Event `whatsapp_click` con condición `page equals carroceria`.
2. Tag Google Ads Conversion → conversión "Contacto WhatsApp carrocería".
3. Tag GA4 Event `generate_lead` → marcar como conversión en GA4 y importar a Ads.
4. Usa `gtm_label` como parámetro para segmentar qué CTA convierte mejor.
