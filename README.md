# L E I L A N I — Website Setup Guide

## 🚀 Publishing to Netlify (Step by Step)

### Step 1 — Create a GitHub Repository
1. Go to github.com and sign up (free)
2. Click **"New Repository"** → name it `leilani-site`
3. Set it to **Public**, click **Create**
4. Upload ALL the files from this zip into the repo (drag & drop into GitHub)

### Step 2 — Deploy on Netlify
1. Go to netlify.com → Sign up with your GitHub account
2. Click **"Add new site"** → **"Import an existing project"**
3. Choose **GitHub** → select your `leilani-site` repo
4. Build settings: leave everything blank (no build command needed)
5. Click **Deploy site** — your site will be live in ~30 seconds!

### Step 3 — Enable the Admin Panel (Netlify CMS)
1. In Netlify dashboard → go to **Site configuration** → **Identity**
2. Click **"Enable Identity"**
3. Scroll down to **"Git Gateway"** → click **"Enable Git Gateway"**
4. Go to **Identity** tab → click **"Invite users"** → invite your own email
5. You'll receive an email — click the link to set your password
6. Your admin panel is now live at: `https://yoursite.netlify.app/admin`

### Step 4 — Add a Custom Domain (Optional)
1. In Netlify → **Domain management** → **Add custom domain**
2. Enter `leilanimusic.com` (or your domain)
3. Follow the DNS instructions to point your domain to Netlify
4. Netlify adds free HTTPS automatically

---

## 🎛️ Using the Admin Panel

Visit `yoursite.com/admin` and log in with your email/password.

### What you can edit:

| Section | What you can change |
|---------|-------------------|
| ⚙️ Site Settings | Artist name, tagline, genre, booking email, all social links |
| 👤 About / Bio | All bio text, pull quote, headings, artist photo |
| 🎵 Music Releases | Add/remove releases, upload artwork, add Spotify/Apple links, set order |
| 🎤 Tour Dates | Add/remove gigs, set sold out status, add ticket URLs |
| 🛍️ Merch Store | Add/remove items, upload product photos, set prices, add purchase links |
| 🌿 Causes | Add/remove fundraisers, update progress amounts, add donation URLs |
| 🖼️ Gallery | Upload/remove photos, add captions |

### How editing works:
1. Log into `/admin`
2. Click the section you want to edit
3. Make your changes in the visual editor
4. Click **"Publish"** — changes go live on your site within ~1 minute

---

## 🛍️ Setting Up Merch Purchasing

For each merch item in the admin, there's a **"Purchase URL"** field.
Paste the direct link to that product on any of these platforms:

- **Shopify** — Full store, most professional (~$29/month)
- **Bandcamp** — Free for artists, great for music + merch
- **Gumroad** — Simple, free to start
- **Printful + Etsy** — Print-on-demand, no inventory needed

When a visitor clicks "Buy Now" on your site, they go directly to that product page to complete the purchase.

---

## 📧 Setting Up the Email List

The email signup form currently shows a confirmation message. To actually collect emails, connect it to one of these (all have free tiers):

- **Mailchimp** — Replace the form action with your Mailchimp embed URL
- **ConvertKit** — Best for musicians, has fan tagging features
- **Netlify Forms** — Simplest option, submissions go to your Netlify dashboard

To enable Netlify Forms (easiest): add `netlify` attribute to the signup form in `index.html`:
```html
<form class="signup-form" netlify name="email-signup">
```
Then view submissions at: Netlify Dashboard → Forms

---

## 📁 File Structure

```
leilani-site/
├── index.html              ← Main website
├── netlify.toml            ← Netlify configuration
├── admin/
│   ├── index.html          ← CMS admin panel
│   └── config.yml          ← CMS field definitions
├── content/
│   ├── settings.json       ← Site-wide settings & social links
│   ├── bio.json            ← Artist bio content
│   ├── gallery.json        ← Gallery photo list
│   ├── releases/           ← One JSON file per release
│   ├── tour/               ← One JSON file per tour date
│   ├── merch/              ← One JSON file per merch item
│   └── causes/             ← One JSON file per cause
└── images/
    ├── gallery/            ← Gallery photos (uploaded via admin)
    ├── merch/              ← Merch product photos
    └── releases/           ← Release artwork
```

---

## ✏️ Adding Your Real Content

Before publishing, update these files with your real info:

1. `content/settings.json` — Add your real social media URLs
2. `content/bio.json` — Replace placeholder bio text with your real bio
3. Add your real tour dates, releases, merch items via the admin panel

---

*Built with Netlify CMS · Hosted on Netlify · © 2025 Leilani Music*
