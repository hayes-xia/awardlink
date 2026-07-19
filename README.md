# AwardLink — Custom Medal Production Partner

One-page B2B website for AwardLink, a zinc alloy medal production partner based in Yiwu, China. Built for trophy shops, awards distributors, and event companies.

## Tech Stack

- **HTML5** single file, zero build tools
- **Tailwind CSS v3** (CDN)
- **Supabase JS Client v2** (CDN) — form backend
- **GitHub Pages** — hosting

## Quick Deploy

1. Fork/clone this repo
2. Set up Supabase (see below)
3. Replace `SUPABASE_URL` and `SUPABASE_ANON_KEY` in `index.html`
4. Push to `main` → GitHub Pages auto-deploys

## Supabase Setup

```sql
CREATE TABLE quotes (
  id BIGSERIAL PRIMARY KEY,
  created_at TIMESTAMPTZ DEFAULT NOW(),
  name TEXT NOT NULL,
  email TEXT NOT NULL,
  company TEXT,
  message TEXT NOT NULL,
  source TEXT DEFAULT 'awardlink.co'
);

ALTER TABLE quotes ENABLE ROW LEVEL SECURITY;
CREATE POLICY "allow_anon_insert" ON quotes
  FOR INSERT TO anon
  WITH CHECK (true);
```

## Custom Domain

After deploying:
1. GitHub repo → Settings → Pages → Custom domain → `awardlink.co`
2. DNS: CNAME record → `<username>.github.io`

## Contact

Hayes Xia · hayes.xia@gmail.com · Yiwu, Zhejiang, China
