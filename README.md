# Sannidhi D Math, portfolio

A single static page: `index.html` and `style.css`. No framework, no build step, no JavaScript, no tracking.

- `index.html`: all content. Critical CSS (colours, base layout, hero) is inlined in `<head>` so the first screen renders without waiting for the stylesheet.
- `style.css`: everything else.
- `cv.pdf`: your CV (the "Download CV" button links to it).
- `assets/`: *(optional)* create this if you add a social preview image (`og:image`).
- `TODO.md`: every placeholder you still need to fill in.

Light and dark mode follow the visitor's system setting (`prefers-color-scheme`).

## Preview locally

From this folder:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploy on GitHub Pages

The site will be served at **https://sannidhi20040.github.io/**. For a user site, the repository name must be exactly `<username>.github.io`.

1. Sign in to GitHub as **Sannidhi20040** and create a new repository at https://github.com/new:
   - Repository name: `Sannidhi20040.github.io`
   - Visibility: **Public** (GitHub Pages on a free account needs a public repo)
   - Leave "Add a README" **unticked** (this folder already has one)
2. Check `cv.pdf` is in this folder (plus `assets/` if you made one).
3. In a terminal, from this folder, run:

   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/Sannidhi20040/Sannidhi20040.github.io.git
   git push -u origin main
   ```

4. On GitHub, open the repo, then **Settings → Pages**. Under **Build and deployment**:
   - Source: **Deploy from a branch**
   - Branch: **main**, folder **/ (root)**, then **Save**
5. Wait a minute or two. The **Actions** tab shows a "pages build and deployment" run; when it turns green, open https://sannidhi20040.github.io/.

**No terminal?** You can instead create the repo (step 1), click **uploading an existing file**, drag in `index.html`, `style.css`, `cv.pdf` and `README.md` (plus `assets/` if you made one), commit, then do step 4.

### Updating the site

Edit the files, then run:

```bash
git add .
git commit -m "Update portfolio"
git push
```

The live site updates within a minute or two. If you still see the old page, force-refresh with Cmd+Shift+R.

## Notes

- `.gitignore` keeps `.claude/` (local preview config) and `.DS_Store` out of the repo.
- If you add images later, keep them small (WebP or JPEG, about 1280 px wide) and give each `<img>` `loading="lazy"`, `width`, `height` and `alt`.
- To check the social preview after adding `og:image`, paste the URL into LinkedIn's Post Inspector: https://www.linkedin.com/post-inspector/
