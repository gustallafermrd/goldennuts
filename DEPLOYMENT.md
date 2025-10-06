Deploying this static site to Vercel

Two quick ways to deploy: GitHub import (recommended) or Vercel CLI.

1. Deploy via Git (GitHub/GitLab/Bitbucket)

- Create a git repo locally (if you don't have one):

```bash
cd /Users/gus/Developer/arabe
git init
git add .
git commit -m "Initial commit - translate + refactor + hero video"
# Create a remote on GitHub and push
git remote add origin git@github.com:<your-user>/<repo>.git
git push -u origin main
```

- Go to https://vercel.com, sign in, click "New Project" → "Import Git Repository", choose your repo, and follow the import form.
- Vercel will detect a static project. If asked, set the build command empty and the output directory to the repository root.

2. Deploy with Vercel CLI (fast, from local machine)

- Install the Vercel CLI (if you don't have it):

```bash
npm i -g vercel
```

- From your project folder:

```bash
cd /Users/gus/Developer/arabe
vercel login
vercel --prod
```

- The CLI will guide you through linking or creating a project and then upload your static files.

Notes & tips

- Make sure paths to assets are relative (they already are: `images/`, `video/`).
- If you want to use a custom domain, configure it in the Vercel dashboard after deployment.
- If your video is large, consider hosting it on a CDN or compressing it; Vercel will serve it but large uploads increase build/deploy time.
- If you want redirects or headers, add them to `vercel.json` under `routes` or `headers`.

If you'd like, I can:

- Create a GitHub Actions workflow to auto-deploy on push.
- Add a small `.vercelignore` to exclude development files.
- Add a small poster image and WebM fallback for the hero video to reduce bandwidth.

Tell me which of the above you'd like me to do next.
