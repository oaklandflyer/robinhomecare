# Robin Home Care – Website Rebuild

A modernised four-page static site for Robin Home Care Ltd., the CQC Outstanding-rated home care service in Ealing and Richmond. Built as part of the ASF Visuals LLC consulting proposal for Ivan.

## What's in here

```
index.html       Home – hero, services overview, story, testimonials, CTA
services.html    Services – six detailed service cards + four-step process
about.html       About – founder story, values, team, credentials
contact.html     Contact – info + working enquiry form + service area map
style.css        Shared stylesheet
```

## Design direction

Warm editorial aesthetic – softer and more human than generic care sector sites.

- **Typography:** Fraunces (display serif, characterful) + Plus Jakarta Sans (body). Deliberately avoids Inter and other generic sans choices.
- **Palette:** Ink blue `#1a2a3a`, cream `#faf6ef`, clay accent `#c97b63`, sage `#6b8e7f`, warm gold `#c9a961`.
- **Signature moves:** Italic Fraunces pull-quotes, CQC Outstanding badge above the fold, offset image frames with clay border outlines, ticker band for services, staggered fade-up on scroll.

## Running locally

No build step. Just open `index.html` in a browser, or serve the folder:

```bash
cd robin-home-care
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Issues this fixes from the current live site

1. **"Pricing 2022"** – removed entirely, replaced with "Book a free consultation" CTA
2. **CQC Outstanding badge buried** – now appears in the hero, in the footer, and as a standalone credential section on the About page
3. **No social links** – Facebook, Instagram, LinkedIn in the footer of every page
4. **No team photography** – About page has a four-person team grid with placeholder photos ready to be replaced
5. **Abandoned blog** – replaced with a more useful "Credentials & compliance" block
6. **Weak primary CTA** – every page now has a clear "Book a consultation" path (hero, nav, CTA band, footer)

## Placeholders to replace before launch

All image URLs currently point to Unsplash and should be swapped for real photography during the Week 3–4 visual production phase of the engagement:

- **Hero image** (`index.html`) – a carer with a client in a West London home
- **Story image** (`index.html`, `about.html`) – real clients or team members
- **Team photos** (`about.html`) – Ivan, Sarah, Priya, Tomasz portraits
- **Map block** (`contact.html`) – replace the styled placeholder with an embedded Google Map centred on the office, or a custom illustrated service-area map

Content to verify with Ivan before launch:

- **Phone number** – currently placeholder `020 8579 1234`
- **Email** – `hello@robin-home-care.co.uk` (assumed from domain)
- **Office address** – placeholder West Ealing W13
- **Team names and bios** – placeholder on About page
- **Testimonial names** – initials used; confirm which real reviews can be quoted and with what attribution
- **Social handles** – `href="#"` currently; plug in real URLs once accounts are set up

## Contact form

The form on `contact.html` currently submits to a no-op and shows a success state client-side. Wire it up to either:

- **Formspree** (lowest friction – same stack as aquadesigncollective.com)
- A Netlify form (if deploying to Netlify)
- A custom endpoint

## Deploying

Matches the ASF Visuals stack: Netlify + Google Workspace email. Drag the folder into Netlify or connect a GitHub repo. Set the custom domain `robin-home-care.co.uk` once Ivan has access to the DNS.

## Browser support

Modern evergreen browsers (Chrome, Safari, Firefox, Edge). Uses `backdrop-filter`, CSS custom properties, grid, `aspect-ratio`, and `IntersectionObserver` – all baseline-supported since 2022.

## Accessibility

- Semantic HTML (`header`, `nav`, `section`, `article`, `footer`)
- WCAG AA contrast ratios throughout (the ink-on-cream pairing is ~15:1)
- Form labels properly associated with inputs
- Focus states inherited from defaults and enhanced on form fields
- `prefers-reduced-motion` respected – all fade-ups and animations disabled
- Skip-link is worth adding at a later iteration
