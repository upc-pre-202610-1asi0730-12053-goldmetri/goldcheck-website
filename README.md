# GoldCheck - The Chain of Trust

Landing page institucional para **GoldCheck**, plataforma de seguridad vehicular inteligente basada en telemetría e IoT.

---

## Estructura del proyecto

```
📁 goldcheck/
├── index.html                  # Página principal
├── style.css                   # Estilos globales
├── README.md                   # Este archivo
├── assets/
│   └── images/
│       ├── goldmetrics-logo.png
│       ├── aesthetic-cover-photo.png   # Fondo del hero
│       ├── mission.jpg
│       ├── vision.jpg
│       └── telemetry.jpg
└── i18n/
    ├── en.json                 # Traducciones en inglés
    └── es.json                 # Traducciones en español
```

---

## Secciones

| Sección | ID | Descripción |
|---|---|---|
| Hero | `#home` | Imagen de fondo con tagline y CTA |
| Mission & Vision | `#about` | Filas alternadas con imagen y texto |
| Benefits | — | Grid de 6 tarjetas |
| Telemetry | `#how` | Descripción técnica con imagen |
| How it works | `#how-works` | Segmentos por tipo de usuario |
| Plans & Pricing | `#pricing` | Planes de suscripción por segmento |
| Contact | `#contact` | Formulario con radio buttons |
| FAQ | `#faq` | Accordion interactivo |

---

## Planes de suscripción

La sección `#pricing` muestra los planes organizados por segmento objetivo mediante tabs interactivos. Incluye un toggle de facturación mensual/anual con descuento del 20%.

### Consumidores
| Plan | Precio | Features principales |
|---|---|---|
| Free | $0 | 5 escaneos QR/mes · Certificado básico · Historial últimas 3 |
| Verifier Pro | $9/mo | Escaneos ilimitados · Historial completo · Alertas · Informe de origen |

### Joyerías
| Plan | Precio | Features principales |
|---|---|---|
| Bronze | $0 | 5 piezas/mes · Dashboard básico · Soporte email |
| Gold ⭐ | $49/mo | 50 piezas/mes · Analytics avanzado · Certificación QR · Soporte prioritario |
| Platinum | $129/mo | Piezas ilimitadas · API access · Multi-empresa · SLA 99.9% · Gerente dedicado |

### Empresas Mineras
| Plan | Precio | Features principales |
|---|---|---|
| Bronze | $0 | 5 lotes/mes · Dashboard básico · Soporte email |
| Gold ⭐ | $49/mo | 50 lotes/mes · Analytics avanzado · IoT tiempo real · Soporte prioritario |
| Platinum | $129/mo | Lotes ilimitados · API access · Multi-empresa · SLA 99.9% · Gerente dedicado |

> Los precios anuales aplican un descuento del 20% (Gold → $39/mo · Platinum → $103/mo).

---

## Cómo correr el proyecto

Este proyecto usa `fetch()` para cargar los archivos de traducción, por lo que **no se puede abrir directamente como archivo HTML**. Necesitas un servidor local.

### Opción 1 — Live Server (VS Code)
1. Instala la extensión **Live Server** en VS Code
2. Click derecho en `index.html` → **Open with Live Server**

### Opción 2 — Python
```bash
python -m http.server 5500
```
Luego abre `http://localhost:5500`

### Opción 3 — Node.js
```bash
npx serve .
```

---

## Internacionalización (i18n)

El sitio soporta **inglés** y **español**. Las traducciones están en `i18n/en.json` y `i18n/es.json`.

Para agregar una nueva clave:
1. Agrega la clave en ambos archivos JSON con la misma estructura
2. Usa `data-i18n="tu.clave"` en el elemento HTML correspondiente

---

## Personalización

### Colores
Las variables CSS están definidas en `:root` dentro de `style.css`:

```css
--color-primary-dark: #2A2A2A;
--color-primary-gold: #C5A059;
--color-secondary-gold: #E2CD9A;
--color-white: #FFFFFF;
--color-dark-text: #1A1A1A;
```

### Imagen de fondo del Hero
Reemplaza el archivo en `assets/images/aesthetic-cover-photo.png` o actualiza la ruta en `style.css`:

```css
.hero-section {
  background: linear-gradient(...), url('assets/images/tu-imagen.png');
}
```

---

## Tecnologías

- HTML5 semántico
- CSS3 con variables y Flexbox
- JavaScript vanilla (sin frameworks)
- Sistema i18n propio con archivos JSON

---

## Commits convencionales

Este proyecto sigue la convención [Conventional Commits](https://www.conventionalcommits.org/):

- `feat:` nueva funcionalidad
- `fix:` corrección de bug o problema visual
- `refactor:` reorganización de código sin cambiar comportamiento
- `docs:` cambios en documentación

---

© 2026 GoldCheck. All rights reserved.