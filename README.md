# Pelham Oaks Dentistry — Demo Site

Mobile-first static site rebuild by Vrynt Lab.
Single-file HTML + referenced image assets. No build step required.

## Local preview

```
# Python 3 (simplest)
python3 -m http.server 8000

# Or Node
npx serve .
```

Then open http://localhost:8000

## Deploy to Cloudflare Pages

1. Push this folder to a GitHub repo:
   ```
   git init
   git add .
   git commit -m "Initial demo build"
   gh repo create pelham-oaks-dentistry-demo --public --source=. --push
   ```

2. Go to https://dash.cloudflare.com → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**

3. Authorize Cloudflare to access your GitHub repos, then pick `pelham-oaks-dentistry-demo`

4. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave blank)*
   - **Build output directory:** `/`
   - **Root directory:** `/` *(leave default)*

5. Click **Save and Deploy**. Live URL returns in ~60 seconds as
   `pelham-oaks-dentistry-demo.pages.dev`

Any push to `main` auto-deploys. Any push to another branch creates a
preview URL like `branch-name.pelham-oaks-dentistry-demo.pages.dev`.

## File structure

```
pelham-oaks-dentistry-demo/
├── index.html               # The site (single-file HTML)
├── _headers                 # Cloudflare Pages cache + security rules
├── robots.txt
├── assets/                  # Logo, photos, badges
│   ├── pelham-oaks-logo-header.png
│   ├── hero-smile.jpg
│   ├── dental-office.jpg
│   ├── dental-chair.jpg
│   ├── family-smile.jpg
│   ├── smile-1.jpg
│   ├── insurance-badges.png
│   └── angies-badge.png
└── README.md
```
