# Intuitive Tarot Reader

A single-page website for an online tarot reading business, built as a fully self-contained HTML file with no external dependencies (beyond Google Fonts).

## Overview

This is a complete client-facing website for **Aanya Sharma**, an intuitive tarot reader based in India. It serves as a booking platform, portfolio, and lead generation tool — designed to convert visitors into WhatsApp enquiries and session bookings.

## Features

- **SPA Routing** — Client-side navigation between Home, Services, Pricing, About, Testimonials, Contact, and Booking pages without any page reloads.
- **Multi-Step Booking Flow** — A 4-step guided booking wizard (Plan → Slot → Details → Confirmation) with visual progress tracking.
- **Responsive Design** — Fully adaptive layout with a mobile bottom navigation bar, hamburger menu, and desktop floating CTAs.
- **WhatsApp Integration** — Primary call-to-action links throughout the site direct users to WhatsApp with a pre-filled message.
- **Scroll Animations** — Intersection Observer–powered reveal animations on all sections.
- **Ambient Visuals** — Floating particles, breathing orb, orbit ring, and shimmer text effects for an atmospheric, mystical aesthetic.

## Tech Stack

| Layer       | Technology                          |
|-------------|-------------------------------------|
| Markup      | HTML5                               |
| Styling     | Vanilla CSS (custom properties)     |
| Logic       | Vanilla JavaScript (no frameworks)  |
| Fonts       | Google Fonts (Cormorant Garamond, DM Sans) |
| Build tools | None — zero build step              |

## Project Structure

The entire site lives in a **single HTML file**:

```
index.html
├── <style>        — All CSS (reset, variables, components, responsive)
├── <nav>          — Fixed navbar with mobile hamburger menu
├── <main id="app">— Dynamic content area (rendered by JS router)
├── <footer>       — Site-wide footer with links and contact info
└── <script>       — Data, routing, page renderers, interactions
```

## Pages

| Route          | Description                                                  |
|----------------|--------------------------------------------------------------|
| `home`         | Hero section, stats, services preview, process steps, testimonials, CTA |
| `services`     | Expandable service cards (Love, Career, Life Path, General)  |
| `pricing`      | 4 plan cards (Quick Insight, Soul Guidance, Elite Clarity, Monthly Support) |
| `booking`      | Multi-step booking wizard                                    |
| `about`        | Reader bio, approach, and philosophy                         |
| `testimonials` | Full client review grid                                      |
| `contact`      | Contact channels + quick message form                        |

## Configuration

All business data is defined in JavaScript constants at the top of the `<script>` block for easy editing:

- **`WA`** — WhatsApp deep link URL (update the phone number here)
- **`PH`** — Phone number `tel:` link
- **`PLANS`** — Pricing tiers (name, price, duration, features)
- **`SERVICES`** — Service offerings (title, descriptions, includes list)
- **`TESTIMONIALS`** — Client reviews (name, location, quote, service type)
- **`FAQS`** — Frequently asked questions (defined but not yet rendered on a dedicated page)

To customise for a different reader, update these constants and the contact details in the navbar, footer, and floating CTA elements.

## Design System

- **Color palette:** Deep purple/black background (`#08060E`), gold accents (`#D4A853`), muted text (`#9B95A0`), WhatsApp green (`#25D366`).
- **Typography:** Cormorant Garamond (serif) for headings and display text; DM Sans for body and UI elements.
- **Components:** Reusable `.card`, `.btn-gold`, `.btn-wa`, `.badge`, `.choice-chip`, `.date-chip`, `.time-chip`, and `.form-input` classes.

## Running Locally

No build step required. Just open the file in a browser:

```bash
open index.html
# or
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Notes

- The booking form is **front-end only** — it does not submit data to a server. The confirmation step directs the user to WhatsApp to finalise the booking.
- The contact form's "Send Message" button triggers a local success state but does not dispatch an email or API call. Connect to a backend or form service (Formspree, EmailJS, etc.) for production use.
- The FAQ data (`FAQS` array) is defined but currently only rendered inline — a dedicated FAQ section can be added by creating a `renderFAQ()` function following the existing pattern.
- The About page includes a placeholder avatar block — replace with an actual photo for production.

## License

Private project. All rights reserved.
