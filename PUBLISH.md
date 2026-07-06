# Publish to GitHub

## Status

| Repo | Local path | GitHub | Notes |
|------|------------|--------|-------|
| **cafe-cursor** | `projects/cafe-cursor` | **[cursorphilly/cafe-cursor](https://github.com/cursorphilly/cafe-cursor)** | Attendee hub |
| **ar-zine-starter** | `projects/zine-ar` | **Live as [zine-ar](https://github.com/luiscielak/zine-ar)** | Rename on GitHub when ready |

AR reader deployed: **https://zine-ar-lemon.vercel.app**

---

## cafe-cursor (attendee hub)

```bash
cd "/Users/luiscielak/Library/Mobile Documents/com~apple~CloudDocs/projects/cafe-cursor"
gh auth login   # if needed
gh repo create cursorphilly/cafe-cursor --public --source=. --remote=origin --push
```

If the repo already exists:

```bash
git push -u origin main
```

---

## ar-zine-starter

Code is on **github.com/luiscielak/zine-ar**. To rename:

1. GitHub → **zine-ar** → Settings → General → **Repository name** → `ar-zine-starter`
2. Update any clone URLs in docs if needed

Or create a new repo and push:

```bash
cd "/Users/luiscielak/Library/Mobile Documents/com~apple~CloudDocs/projects/zine-ar"
gh repo create luiscielak/ar-zine-starter --public --source=. --remote=ar-starter --push
```

---

## Redeploy AR reader after changes

```bash
cd "/Users/luiscielak/Library/Mobile Documents/com~apple~CloudDocs/projects/zine-ar"
npm run make-cafe-pages    # optional: regenerate spread art
npm run compile-targets    # rebakes cover QR + zine.mind
vercel --prod
```

Update `src/site-config.js` `READER_URL` if the production URL changes, then re-run `compile-targets` and redeploy.
