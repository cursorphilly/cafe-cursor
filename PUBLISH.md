# Publish to GitHub

Local repos are ready. Create the remote repositories and push:

## cafe-cursor (attendee hub)

```bash
cd "/Users/luiscielak/Library/Mobile Documents/com~apple~CloudDocs/projects/cafe-cursor"
gh auth login   # if needed
gh repo create luiscielak/cafe-cursor --public --source=. --remote=origin --push
# Or if repo exists:
git push -u origin main
```

## ar-zine-starter (from zine-ar)

```bash
cd "/Users/luiscielak/Library/Mobile Documents/com~apple~CloudDocs/projects/zine-ar"
gh repo create luiscielak/ar-zine-starter --public --source=. --remote=ar-starter --push
# Or rename remote and push:
git remote add ar-starter git@github.com:luiscielak/ar-zine-starter.git
git push -u ar-starter main
```

The existing `origin` remote points at `luiscielak/zine-ar` if you prefer to keep that name and add `ar-zine-starter` as a new repo.

## Deploy AR reader (Vercel)

```bash
cd "/Users/luiscielak/Library/Mobile Documents/com~apple~CloudDocs/projects/zine-ar"
npm run make-cafe-pages
npm run compile-targets
vercel --prod
# Update src/site-config.js READER_URL with the production URL, then re-run compile-targets and redeploy.
```
