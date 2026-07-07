# GoldCheck - The Chain of Trust

Institutional landing page for **GoldCheck**, a gold traceability platform that connects
miners, jewelry stores and consumers through IoT telemetry, QR certification and transparent
supply-chain tracking.

---

## Project structure

```
📁 goldcheck-website/
├── index.html                  # Main page (markup + vanilla JS)
├── style.css                   # Global styles
├── README.md                   # This file
├── assets/
│   └── images/
│       ├── goldmetrics-logo.png
│       ├── favicon.svg
│       ├── aesthetic-cover-photo.png   # Hero background
│       ├── mission-cover.png           # Mission section
│       ├── vision.png                  # Vision section
│       ├── jewerly.png                 # Telemetry section
│       ├── user-1-anthony.jpeg         # Testimonial – mining user
│       ├── user-2-yesiliany.jpeg       # Testimonial – jewelry user
│       └── user-3-carla.jpeg           # Testimonial – final consumer
└── i18n/
    ├── en.json                 # English translations
    └── es.json                 # Spanish translations
```

---

## Sections

| Section | ID | Description |
|---|---|---|
| Hero | `#home` | Background image with tagline and CTA |
| Mission & Vision | `#about` | Alternating rows with image and text |
| Benefits | — | Grid of 6 cards |
| Telemetry | `#how` | Technical description with image |
| How it works | `#how-works` | Segments by user type |
| Videos | `#videos` | Embedded YouTube videos ("About the Team" and "About the Product") |
| Success Stories | `#testimonials` | Testimonials carousel with navigation controls |
| Plans & Pricing | `#pricing` | Subscription plans per segment |
| FAQ | `#faq` | Interactive accordion |
| Contact | `#contact` | Form with field-level validation |

---

## Key features & interactivity

- **Responsive navigation** — below 992px the header collapses into a hamburger menu that groups
  the nav links, the language switcher and the auth buttons, keeping the top bar clean on mobile.
- **Videos section** — responsive 16:9 YouTube embeds (privacy-friendly `youtube-nocookie`,
  lazy-loaded) that stack on mobile and sit side by side on desktop.
- **Success Stories carousel** — accessible testimonials slider with previous/next arrows and
  dot controls (wrap-around), showing a photo, name and role for each customer.
- **Contact form validation** — field-level validation that highlights and focuses the first
  invalid field, shows a specific localized message, validates the email format, and clears the
  error as soon as the user edits the field.
- **Auth CTAs** — "Login" links to the app's `/#/auth/login` route and the sign-up / hero / plan
  CTAs link to `/#/auth/register` (configured via the `data-app-link` attribute).
- **Internationalization** — English/Spanish switch with a lightweight custom i18n system.
- **Extras** — scroll-reveal animations (respecting `prefers-reduced-motion`), sticky navbar with
  scroll state, active-section highlighting and a back-to-top button.

---

## Subscription plans

The `#pricing` section shows the plans grouped by target segment via interactive tabs. It includes
a monthly/annual billing toggle with a 20% discount.

### Consumers
| Plan | Price | Main features |
|---|---|---|
| Free | $0 | 5 QR scans/month · Basic certificate · Last 3 verifications |
| Verifier Pro | $9/mo | Unlimited scans · Full history · Alerts · Origin report |

### Jewelry Stores
| Plan | Price | Main features |
|---|---|---|
| Bronze | $0 | 5 pieces/month · Basic dashboard · Email support |
| Gold ⭐ | $53/mo | 50 pieces/month · Advanced analytics · QR certification · Priority support |
| Platinum | $133/mo | Unlimited pieces · API access · Multi-company · SLA 99.9% · Dedicated manager |

### Mining Companies
| Plan | Price | Main features |
|---|---|---|
| Bronze | $0 | 5 batches/month · Basic dashboard · Email support |
| Gold ⭐ | $53/mo | 50 batches/month · Advanced analytics · Real-time IoT · Priority support |
| Platinum | $133/mo | Unlimited batches · API access · Multi-company · SLA 99.9% · Dedicated manager |

> Annual pricing applies a 20% discount (Gold → $42/mo · Platinum → $106/mo). Jewelry and Mining
> prices match the web app's S/199 and S/499 monthly plans, converted to USD.

---

## Running the project

This project uses `fetch()` to load the translation files, so it **cannot be opened directly as an
HTML file**. You need a local server.

### Option 1 — Live Server (VS Code)
1. Install the **Live Server** extension in VS Code
2. Right-click `index.html` → **Open with Live Server**

### Option 2 — Python
```bash
python -m http.server 5500
```
Then open `http://localhost:5500`

### Option 3 — Node.js
```bash
npx serve .
```

---

## Internationalization (i18n)

The site supports **English** and **Spanish**. Translations live in `i18n/en.json` and
`i18n/es.json`.

To add a new key:
1. Add the key in both JSON files with the same structure
2. Use `data-i18n="your.key"` on the corresponding HTML element

---

## Customization

### App URL & routes
The external web-app URL and its auth routes are defined at the top of the `<script>` in
`index.html`:

```js
const APP_URL = 'https://goldcheck-goldmetrics.netlify.app';
const APP_ROUTES = {
  login: '/#/auth/login',
  register: '/#/auth/register'
};
```

### Colors
CSS variables are defined in `:root` inside `style.css`:

```css
--color-primary-dark: #2A2A2A;
--color-primary-gold: #C5A059;
--color-secondary-gold: #E2CD9A;
--color-white: #FFFFFF;
--color-dark-text: #1A1A1A;
```

### Hero background image
Replace `assets/images/aesthetic-cover-photo.png` or update the path in `style.css`:

```css
.hero-section {
  background: linear-gradient(...), url('assets/images/your-image.png');
}
```

---

## Tech stack

- Semantic HTML5
- CSS3 with variables, Flexbox and Grid
- Vanilla JavaScript (no frameworks)
- Custom i18n system with JSON files

---

## Conventional commits

This project follows the [Conventional Commits](https://www.conventionalcommits.org/) convention:

- `feat:` new feature
- `fix:` bug or visual fix
- `refactor:` code reorganization without behavior changes
- `docs:` documentation changes

---

© 2026 GoldCheck. All rights reserved.
