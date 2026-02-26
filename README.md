# Wedding Invite (React + Vite)

Static wedding invite site built with React + Vite.

## Local Development

Requirements:
- Node.js 18+
- npm

Install and run:

```bash
npm install
npm run dev
```

Build for production:

```bash
npm run build
```

## GitHub Pages Deployment

This repo is configured as a GitHub **user site** (`capevrob.github.io`), so Vite base is:

```js
base: "/"
```

Deployment uses GitHub Actions via:

`/.github/workflows/deploy.yml`

### Steps

1. Push to `master` (or `main`):

```bash
git add .
git commit -m "Update site"
git push
```

2. In GitHub:
- Go to `Settings -> Pages`
- Set **Source** to **GitHub Actions**

3. Wait for the `Deploy to GitHub Pages` action to complete successfully.

4. Open:

`https://capevrob.github.io/`

## Troubleshooting

If you see a white page and browser error:

`Failed to load module script ... MIME type of "text/jsx"`

It means Pages is serving source files (like `/src/main.jsx`) instead of built `dist` files.

Fix:
- Ensure `Settings -> Pages -> Source` is set to `GitHub Actions`
- Re-push to trigger deploy
- Hard refresh (`Cmd+Shift+R` on Mac / `Ctrl+Shift+R` on Windows/Linux)

Expected built script path in page source should look like:

`/assets/index-*.js`

not:

`/src/main.jsx`
