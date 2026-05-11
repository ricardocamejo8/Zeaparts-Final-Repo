# Zeaparts.cl

Sitio web de Zeaparts SPA — Especialistas en repuestos Chevrolet Spark, Aveo y Sail.

Estático, sin build step. HTML + CSS + JS vanilla.

## Estructura

```
/
├── index.html                  # Landing principal
├── politica-privacidad.html    # Política de privacidad (Ley 19.628)
├── politica-envio.html         # Política de envío (Ley 19.496)
├── contacto.html               # Información de contacto
├── assets/
│   ├── logo-zeaparts.png       # Logo principal
│   ├── hero-spark.jpg          # Banner del hero
│   └── legal.css               # Estilos compartidos páginas legales
├── vercel.json                 # Configuración de Vercel (clean URLs, headers, redirects)
├── robots.txt
└── sitemap.xml
```

## Despliegue en Vercel

### Opción A — Vercel CLI (más rápida)

```bash
npm i -g vercel
cd zeaparts
vercel              # primera vez: crea el proyecto
vercel --prod       # despliegue productivo
```

### Opción B — Conectar repo Git

1. Sube esta carpeta a un repo de GitHub / GitLab / Bitbucket.
2. En [vercel.com](https://vercel.com/new) → **Import Project** → selecciona el repo.
3. Framework Preset: **Other** (es estático puro). Build Command: vacío. Output Directory: vacío (raíz).
4. Deploy.

### Opción C — Drag & Drop

1. [vercel.com/new](https://vercel.com/new) → arrastra la carpeta completa.

## Dominio personalizado (zeaparts.cl)

1. En Vercel → Project Settings → Domains → añade `zeaparts.cl` y `www.zeaparts.cl`.
2. En tu proveedor de dominios (NIC Chile o equivalente), apunta:
   - `A` record `@` → `76.76.21.21`
   - `CNAME` `www` → `cname.vercel-dns.com`
3. Vercel emite el certificado SSL automáticamente.

## Cosas a actualizar antes de producción

- [ ] `assets/logo-zeaparts.png` — confirmar versión final del logo
- [ ] Horario real de la tienda (hoy está como "consultar")
- [ ] Reemplazar testimonios placeholder por reales (o quitar la sección)
- [ ] Cambiar `<meta property="og:url">` y schema URLs por el dominio definitivo si distinto
- [ ] Agregar `og:image` (1200×630) en `assets/og.jpg`
- [ ] Verificar Google Maps embed: la URL larga oficial dará mejor precisión que el query simple

## Tweaks en producción

El panel de "Tweaks" se activa solo desde el editor visual del proyecto (no es público). En el sitio publicado los visitantes no lo ven.

## Stack

- HTML5 estático
- CSS vanilla (sin frameworks, sin build)
- JavaScript vanilla (sin dependencias)
- Google Fonts: Rajdhani · Inter · JetBrains Mono
- Schema.org JSON-LD (`AutoPartsStore`)
