# The Dining Atelier

The Dining Atelier is a Next.js website with a home page, about page, services, work, testimonials, and a contact form.

## Pages

| Route | Page |
| --- | --- |
| `/` | Home |
| `/about` | About |
| `/services` | Services |
| `/work` | Work |
| `/testimonials` | Testimonials |
| `/contact` | Contact |

The header shows the brand name and links to YouTube, Instagram, Facebook, Dribbble, Pinterest, and GitHub.

## Contact form

The contact page posts to `POST /api/contact`. The request includes the visitor's name, email, subject, message, and a reCAPTCHA v3 token.

The API checks the form fields and the reCAPTCHA score, then sends two emails through [Resend](https://resend.com):

- A thank-you to the visitor, from `hello@thediningatelier.com`
- A notification to `reservations@thediningatelier.com`

## Tech

- Next.js 16
- React 19
- Tailwind CSS 4
- Framer Motion
- Swiper
- tsParticles

## Getting started

1. Install [Node.js](https://nodejs.org) and [pnpm](https://pnpm.io).
2. Install dependencies:

```bash
pnpm install
```

3. Copy `.env.example` to `.env.local` and fill in the keys. Contact addresses used by this site:

```env
RESEND_FROM_EMAIL="The Dining Atelier <hello@thediningatelier.com>"
CONTACT_TO_EMAIL="reservations@thediningatelier.com"
CONTACT_SITE_URL="https://thediningatelier.com"
```

`RESEND_API_KEY`, the two Resend template ids, and the Google reCAPTCHA v3 keys are also required. The contact form stays unavailable until `NEXT_PUBLIC_RECAPTCHA_SITE_KEY` is set. Do not commit `.env.local`.

4. Start the site:

```bash
pnpm dev
```

Other scripts:

| Script | Command |
| --- | --- |
| Development | `pnpm dev` |
| Production build | `pnpm build` |
| Production server | `pnpm start` |
| Lint | `pnpm lint` |

## Folder map

```text
app/
  about/
  api/contact/
  contact/
  services/
  testimonials/
  work/
  globals.css
  layout.tsx
  page.tsx
  template.tsx
components/
lib/contact.ts
public/
variants.ts
```
