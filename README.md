# Ironwood Construction Group — Website Setup

3 things to do before/after deploying. Takes about 10 minutes total.

## 1. Deploy to Vercel (2 min)

1. Go to [vercel.com/new](https://vercel.com/new)
2. Drag and drop this entire `ironwood-website` folder onto the page (or import via Git)
3. Click **Deploy** — no build settings needed, it's a static site
4. In the project: **Settings → Domains → Add** → enter `ironwoodconstructiongroupllc.com` and follow the DNS instructions Vercel gives you (you'll add an A record / CNAME at your domain registrar)

## 2. Connect the lead form (3 min) — REQUIRED

The form uses Web3Forms (free, submissions go to your email).

1. Go to [web3forms.com](https://web3forms.com) and enter the email where you want leads delivered → it emails you an **Access Key**
2. Open `index.html`, find this line (near the form):
   ```
   <input type="hidden" name="access_key" value="YOUR_WEB3FORMS_ACCESS_KEY">
   ```
3. Replace `YOUR_WEB3FORMS_ACCESS_KEY` with your key. Redeploy.

Until you do this, the form shows a "not connected yet" message instead of sending.

## 3. Add your photos

Create an `images/` folder next to `index.html` with these files (JPG, ideally 1200px wide or larger, compressed — use [squoosh.app](https://squoosh.app)):

| Filename | Used for |
|---|---|
| `hero.jpg` | Background of the top banner (wide shot of a finished roof/home works best) |
| `about.jpg` | About section (crew or job-site photo) |
| `project-1.jpg` … `project-6.jpg` | Work gallery |

The site looks fine before photos are added (broken images auto-hide), but real photos dramatically improve conversion. You can also rename the gallery captions in `index.html` to match your actual projects/cities.

## After launch — SEO checklist

- **Google Business Profile**: create/claim one at [google.com/business](https://google.com/business) for "Ironwood Construction Group LLC, Tomball TX" — this matters more than anything else for local search
- **Google Search Console**: add the site at [search.google.com/search-console](https://search.google.com/search-console), verify the domain, and submit `sitemap.xml`
- Ask happy customers for Google reviews — reviews + the site's schema markup drive local rankings
- The site already includes: LocalBusiness + RoofingContractor structured data, FAQ schema, 40-city service area targeting, mobile click-to-call bar, Open Graph tags, sitemap, robots.txt

## Files

- `index.html` — the entire website (HTML + CSS + JS, no dependencies)
- `robots.txt`, `sitemap.xml` — SEO support files
- `images/` — you create this and add photos
