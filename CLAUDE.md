# ITA Contadores - Sitio Web

## Proyecto
Sitio web corporativo para **ITA Contadores**, firma contable mexicana con +17 años de experiencia. La clienta (propietaria) hizo un prototipo en Base44 que usamos como referencia para mejorar el diseño y construir la versión profesional.

## Stack
- **Astro v6** - Framework estático (output: static)
- **Tailwind CSS v4** - Estilos vía `@tailwindcss/vite` plugin
- **TypeScript** - Modo strict
- **Hosting**: Neubox (shared hosting, solo archivos estáticos en `dist/`)

## Comandos
```bash
npm run dev      # Dev server en localhost:4321
npm run build    # Build estático → dist/
npm run preview  # Preview del build
```

## Estructura
```
src/
├── layouts/Layout.astro       # Layout base (fonts, meta, global CSS)
├── styles/global.css          # Tailwind @theme con colores y fuentes de marca
├── components/
│   ├── Navbar.astro           # Nav sticky con menú hamburguesa mobile
│   ├── Hero.astro             # Hero con imagen de fondo, CTAs, card flotante
│   ├── StatsBar.astro         # Barra de estadísticas (17+, 20+, <24h, 100%)
│   ├── ClientLogos.astro      # Marquee infinito de logos clientes
│   ├── Propuesta.astro        # 4 cards de propuesta de valor
│   ├── Servicios.astro        # Tabs interactivos (Fiscal, Contabilidad, Admin, Alianzas)
│   ├── Diferenciadores.astro  # Sección navy "Lo que nos hace diferentes"
│   ├── Historia.astro         # Nuestra historia con foto
│   ├── QuienesSomos.astro     # Tabs (Quiénes somos, Misión, Visión, Valores)
│   ├── Resultados.astro       # Casos de éxito (35%, 100%, 0%)
│   ├── Diagnostico.astro      # CTA diagnóstico fiscal gratuito
│   ├── Calculadora.astro      # Calculadora fiscal con JS
│   ├── Portales.astro         # 8 portales gobierno (SAT, IMSS, etc.)
│   ├── Blog.astro             # 3 artículos preview
│   ├── CtaBand.astro          # Banda CTA con WhatsApp
│   ├── Contacto.astro         # Formulario + info de contacto
│   └── Footer.astro           # Footer con 4 columnas
└── pages/
    └── index.astro            # Página principal (ensambla todos los componentes)
```

## Design System / Marca

### Colores (definidos en global.css @theme)
| Token            | Hex       | Uso                                    |
|------------------|-----------|----------------------------------------|
| `--color-azul`   | `#1E1B4B` | Títulos, fondos fuertes, gradientes    |
| `--color-azul-light` | `#312E81` | Gradientes (destino)              |
| `--color-azul-medio` | `#2F5F8F` | Textos secundarios importantes    |
| `--color-verde`  | `#4CAF7A` | Labels, links, secciones destacadas    |
| `--color-amarillo` | `#F2C94C` | Botones CTA principales              |
| `--color-gris`   | `#64748B` | Texto de cuerpo                        |
| `--color-bg`     | `#F8FAFC` | Fondos de secciones alternadas         |
| `--color-border` | `#E2E8F0` | Bordes de cards                        |

### Tipografía
- **Montserrat** (700/800) → Títulos, headings, nombres de sección, botones CTA
- **Montserrat** (600) → Labels, tabs, badges, nav links
- **Open Sans** (400) → Párrafos, descripciones, textos de cuerpo

### Patrones de diseño
- Secciones alternan fondo blanco / `#F8FAFC` / gradiente navy
- Labels de sección: verde, uppercase, tracking-widest, 12px, Montserrat 600
- Títulos de sección: 38px, Montserrat 700, a veces italic
- Cards: white bg, border `#E2E8F0`, rounded-2xl, padding 28-32px
- CTAs principales: bg amarillo `#F2C94C`, texto azul `#2B2A5A`, rounded-full
- CTAs secundarios: outline, border white/40%, rounded-full

## Imágenes
- `public/images/hero.jpg` - Edificios corporativos para fondo del hero
- `public/images/nuestra-historia.jpg` - Foto de la fundadora
- `public/images/logo.png` - Logo principal
- `public/images/logo-navbar.png` - Logo para el navbar
- `public/images/favicon.png` - Favicon
- `public/images/clientes/` - 20 logos de empresas clientes

## Interactividad (vanilla JS)
- **Servicios.astro**: tabs que cambian contenido del panel derecho
- **QuienesSomos.astro**: tabs para Quiénes somos / Misión / Visión / Valores
- **Calculadora.astro**: cálculo fiscal básico por régimen
- **Navbar.astro**: menú hamburguesa mobile + shadow on scroll

## Info de contacto (para componentes)
- Dirección: Hornillos #5, Col. Santa Cecilia, Tlalnepantla 54130
- Email: mtrujillo@itacontadores.com
- Teléfono: 55 59 20 23 11
- Horario: Lunes a Viernes, 9:00 AM - 6:00 PM

## Convenciones
- Un componente por sección de la página
- Los componentes no tienen props; son auto-contenidos con datos hardcodeados
- Iconos: SVG inline (estilo Lucide)
- IDs de sección para navegación: hero, propuesta, servicios, nosotros, blog, contacto
- Mobile-first responsive con breakpoints lg: para desktop
