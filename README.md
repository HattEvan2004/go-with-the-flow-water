# Go With The Flow Water Delivery — Landing Page

A fast, responsive, single-page website for **Go With The Flow Water Delivery**, serving
Lunenburg County, NS with bulk water delivery for cisterns, pools, hot tubs, and wells.

It's a plain static site — just `index.html` plus an `assets/` folder. No build step, no
framework, no dependencies. That means it deploys to Vercel (or Netlify, GitHub Pages, etc.)
with zero configuration.

```
.
├── index.html        ← the whole site
├── assets/
│   ├── logo.png       ← brand logo (header + footer)
│   ├── truck.jpg      ← hero photo
│   ├── pool-fill.jpg  ← showcase photo
│   └── tanker.jpg     ← showcase photo
└── README.md
```

---

## View it locally

Just open `index.html` in any browser. (For the cleanest result you can run a tiny local
server so paths and fonts behave exactly like production:)

```bash
# Python 3
python3 -m http.server 8000
# then visit http://localhost:8000
```

---

## Put it on GitHub

1. Create a new repository on GitHub (e.g. `go-with-the-flow-water`). Leave it empty.
2. In this folder, run:

   ```bash
   git init
   git add .
   git commit -m "Initial landing page"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/go-with-the-flow-water.git
   git push -u origin main
   ```

   (Replace the URL with the one GitHub shows you.)

---

## Deploy to Vercel

1. Go to **vercel.com** and sign in with GitHub.
2. Click **Add New → Project**, then **Import** the repository you just pushed.
3. Framework preset: **Other** (it's a static site). Leave Build Command and Output
   Directory **blank**. Click **Deploy**.
4. Done — Vercel gives you a live URL in a few seconds. Every future `git push` to `main`
   redeploys automatically.

### Custom domain (optional)
In your Vercel project: **Settings → Domains → Add**, enter the domain (e.g.
`gowiththeflowwater.ca`), and follow the DNS steps Vercel shows.

---

## Make the contact form actually send

Right now the form is front-end only: it validates and shows a "thank you" message, but
nothing is emailed anywhere. To receive real submissions, the easiest no-server option is
[Formspree](https://formspree.io):

1. Create a free Formspree form and copy your form ID.
2. In `index.html`, find `<form id="leadForm" novalidate>` and change it to:

   ```html
   <form id="leadForm" action="https://formspree.io/f/YOUR_ID" method="POST">
   ```

3. Remove (or keep) the JavaScript submit handler near the bottom. Formspree will email
   you every submission. Other options: Netlify Forms, Vercel + a serverless function, or
   wiring it to your own email/CRM.

---

## Things you'll probably want to update

All of these live in `index.html`:

- **Email address** — `dispatch@gowiththeflowwater.ca` is a placeholder. Search and replace
  it with your real email.
- **Hours** — in the "Hours" card in the Contact section.
- **Service-area towns** — the list of communities in the Service Area section.
- **Phone number** — set to `(902) 212-1296` (also as `tel:+19022121296`). Search and
  replace if it ever changes.

> Tip: the phone number appears in several places (header, hero, emergency section,
> contact card, footer, mobile call bar). A find-and-replace for `212-1296` and
> `+19022121296` catches them all.

---

© Go With The Flow Water Delivery. Built as a custom single-page site.
