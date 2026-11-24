# B_K WORLD — Website Project

A mobile-friendly social community starter with a black / metallic / red B_K identity.

## Included
- Responsive home feed and search
- Create text/photo/video posts (Supabase-backed after setup)
- Email/password sign-up and login
- User profile editing
- Likes table and share-link action
- Supabase SQL schema, auth profile trigger, Row Level Security policies
- Public post-media storage bucket with per-user upload folders
- Demo preview when Supabase credentials are not configured

## Important status
This ZIP is a working front-end starter. Real public accounts, shared posts and cloud uploads become active only after you create a Supabase project, run `supabase/schema.sql`, and add your project URL and anon/public key to `app.js`. Do not put a Supabase `service_role` key in browser code. Messaging, notifications, full reels player, moderation dashboard, and advanced creator analytics are planned next modules, not active features in this starter.

## 1. Create backend
1. Open https://supabase.com/ and create a project.
2. In Project Settings → API, copy the Project URL and `anon` / publishable key.
3. Open SQL Editor → New query.
4. Paste and run all of `supabase/schema.sql`.

## 2. Connect website
Open `app.js` and replace:
- `SUPABASE_URL = ""` with your Project URL
- `SUPABASE_ANON_KEY = ""` with your anon/public key

Never use the `service_role` secret in the website.

## 3. Run locally
You can open `index.html` for a preview. For best results, serve the folder with a static web server, or upload it to Cloudflare Pages.

## 4. Publish on Cloudflare Pages
1. Create a Git repository and upload the contents of this folder.
2. In Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git.
3. Select the repository.
4. Framework preset: None. Build command: leave blank. Output directory: `/` (or the repository root).
5. Deploy.

You can also use another static host that supports plain HTML/CSS/JS.

## 5. Supabase Auth redirect URLs
In Supabase → Authentication → URL Configuration:
- Site URL: your deployed website URL
- Add your deployed URL to Redirect URLs.
- During testing, add your local preview URL as well.

## Before inviting the public
- Configure email confirmation and password reset.
- Add Terms, Privacy Policy, Community Guidelines and a support contact.
- Set up report/block flows and moderator/admin tools.
- Test RLS policies with separate test accounts.
- Add rate limits, content moderation, backup/retention and abuse handling.
- Review the privacy and child-safety requirements for your intended audience.

## Project structure
- `index.html` — app shell and dialogs
- `styles.css` — responsive red/black design
- `app.js` — front-end logic and Supabase connection
- `supabase/schema.sql` — database, trigger, RLS and storage setup
- `assets/bk-logo.png` — selected B_K logo
- `.env.example` — configuration reminder
