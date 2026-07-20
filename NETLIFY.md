# Netlify deployment instructions

This repository contains a static HTML site (index siam.html). The following notes explain how to connect and deploy this repository to Netlify.

1) Connect the repository in Netlify UI
   - Go to https://app.netlify.com/sites
   - Click "New site from Git" and choose GitHub, then select the Siam1207/siamtarafder repository.
   - For "Build command" leave empty (no build step required for raw HTML) or enter your build command if you add a build step later.
   - For "Publish directory" set: `.` (the repository root)
   - In Site settings > General > Site details, you can confirm the Site ID matches:
     `7954e74a-c9d8-4482-8f80-d9296b3b8b49`

2) Deploy from CLI (optional)
   - Install Netlify CLI: `npm install -g netlify-cli`
   - Login: `netlify login`
   - Deploy a draft: `netlify deploy --dir=. --site=7954e74a-c9d8-4482-8f80-d9296b3b8b49`
   - Deploy to production: `netlify deploy --prod --dir=. --site=7954e74a-c9d8-4482-8f80-d9296b3b8b49`

3) Environment variables / Continuous deploy (optional)
   - If you need environment variables or a build command, add them in Site > Build & deploy > Environment.
   - The `netlify.toml` file included in this repo sets `NETLIFY_SITE_ID` in the production context. Adjust as needed.

4) Notes about the site
   - The main HTML file in the repo is named `index siam.html`. Netlify expects `index.html` by default. Consider renaming `index siam.html` to `index.html` or adding a redirect/rewrites rule if you want it to serve automatically at the root.
   - If you prefer to keep the filename, create a simple `index.html` that redirects to `index%20siam.html` or rename locally and push the change.

If you'd like, I can also:
- Add a CI workflow to run Netlify CLI deploys on push (requires a Netlify Auth token)
- Rename `index siam.html` to `index.html` and update any links so the site serves at the root automatically
- Add common rewrite/redirect rules or an _redirects file

Tell me which of the above you'd like me to do next.
