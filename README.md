# The Bottle Shoppe

Static website for The Bottle Shoppe — a neighborhood liquor store in Shorewood, MN.
Hosted on GitHub Pages at [www.thebottleshoppemn.com](https://www.thebottleshoppemn.com).

---

## Pages

| File | Description |
|---|---|
| `index.html` | Homepage — hero, delivery section, product categories, contact form |
| `inventory.html` | Coming Soon page — placeholder until digital inventory is ready |
| `about.html` | About / Our Story page |
| `style.css` | Shared stylesheet |

---

## TODO: Activate the Contact Form (Formspree)

The contact form on the homepage is built and styled but needs a **free Formspree account** to receive submissions. Follow these steps:

### Step 1 — Create a Formspree account
1. Go to [https://formspree.io](https://formspree.io)
2. Click **Get Started** and sign up with `tbs.shorewood@gmail.com`

### Step 2 — Create a new form
1. In your Formspree dashboard, click **+ New Form**
2. Give it a name (e.g. `The Bottle Shoppe Contact`)
3. Set the email to `tbs.shorewood@gmail.com`
4. Click **Create Form**

### Step 3 — Copy your Form ID
After creating the form, Formspree will show you an endpoint like:
```
https://formspree.io/f/xpwzabcd
```
Your **Form ID** is the last part — e.g. `xpwzabcd`

### Step 4 — Update index.html
Open `index.html` and find this line (around line 128):
```html
action="https://formspree.io/f/YOUR_FORM_ID"
```
Replace `YOUR_FORM_ID` with your actual ID:
```html
action="https://formspree.io/f/xpwzabcd"
```

### Step 5 — Commit and push
```bash
git add index.html
git commit -m "Activate Formspree contact form"
git push
```

### Step 6 — Test it
1. Visit [www.thebottleshoppemn.com](https://www.thebottleshoppemn.com) and scroll to the Contact Us section
2. Submit a test message
3. Check `tbs.shorewood@gmail.com` — you should receive the message within a minute

> **Free tier limits:** Formspree free allows 50 submissions/month. More than enough for a contact form.

---

## Updating Content

### Logo
Replace `images/logo.png` with a new PNG file keeping the same filename.

### Store hours / address / phone
Search all `.html` files for the relevant text and update in place. Hours appear in both the footer (all pages) and the Coming Soon hero (`inventory.html`).

### Inventory page
When ready to show real inventory, replace `inventory.html` with a product listing page. A product data-driven version using `inventory.json` is preserved in the git history.

---

## Local Development

No build step required — open any `.html` file directly in a browser, or use a simple local server:

```bash
# Python
python -m http.server 8000

# Node (npx)
npx serve .
```

Then visit `http://localhost:8000`.

---

## Deployment

The site deploys automatically via **GitHub Pages** on every push to `main`.

Custom domain is configured via the `CNAME` file:
```
www.thebottleshoppemn.com
```

DNS should have a `CNAME` record pointing `www` → `nicholas-pds.github.io`.
