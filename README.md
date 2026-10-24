# Intelligent Systems & Technology: portfolio

A static portfolio site (HTML, CSS, vanilla JavaScript). No build step.

## Structure

```
index.html        page markup
css/style.css     all styles
js/config.js      your email, phone and profile links (edit this first)
js/data.js        skills, projects and process steps
js/main.js        rendering, navigation, modal, contact form
assets/           project illustrations and favicon
vercel.json       Vercel settings (headers, clean URLs)
```

## Before you deploy

1. Open `js/config.js` and add your LinkedIn and GitHub URLs. Until you do, those buttons and icons stay hidden. Email and phone numbers are already set there.
2. Optional: add a portrait as `assets/profile.jpg` (square, at least 320 x 320 px). Until then the page shows your initials.
3. Check each project's status in `js/data.js`. Every project is currently labelled "Prototype built" or "Dissertation project". To show a proposed idea, add a project with `kind: "proposed"` and the filter buttons appear automatically. If one has since been built, change its `kind`, `badge` and `statusNote`.

## Run locally

```
npx serve .
```

or open `index.html` directly in a browser.

## Deploy on Vercel

Using the dashboard: push this folder to a GitHub repository, choose "Add New Project" in Vercel, import the repository and click Deploy. Leave the framework preset as "Other" and the build command and output directory empty.

Using the CLI:

```
npm i -g vercel
vercel --prod
```

## Make the contact form send email

The form sends the visitor's name, email and message straight to your inbox using Web3Forms (free, no server needed).

1. Go to https://web3forms.com and enter `niyopaul12345@gmail.com` to create an access key. The key is emailed to you.
2. Open `js/config.js` and paste the key between the quotes of `formAccessKey`.
3. Redeploy. Submitting the form now delivers the message to your inbox, and you can reply directly to the sender.

The key is safe to keep in public code: it can only send messages to your own email address. Until a key is added, the form falls back to opening the visitor's email app.

Prefer Formspree? Set `formEndpoint` to your Formspree form URL (`https://formspree.io/f/...`) and leave `formAccessKey` empty.

## Professional polish notes

- `assets/*.webp`: project photos are WebP (about half the size of the old JPGs). `assets/og-image.png` is the 1200x630 social preview.
- `robots.txt` is included. Add a `sitemap.xml` once you have your final domain.
- After deploying, change the `og:image` and `twitter:image` meta tags in `index.html` to the absolute URL, for example `https://your-domain.vercel.app/assets/og-image.png`. Social sites need the full address.
- The architecture diagram in "Technical approach" is illustrative. It shows the typical layers of my systems and no live data.
- LinkedIn and GitHub icons stay hidden until you fill `linkedin` and `github` in `js/config.js`.
- The site has no contact form. Visitors reach you by email, phone, WhatsApp and the profile links.
