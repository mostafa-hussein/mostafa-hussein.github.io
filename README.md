# Personal website

My research and portfolio site, built on the [al-folio](https://github.com/alshedivat/al-folio) Jekyll template and hosted free on GitHub Pages.

Pages: **about** (home) · **publications** · **projects** · **CV** · news (on the home page).

Search the repo for `TODO` to find every placeholder that still needs real content.

## Where everything goes

| What | File | Notes |
| --- | --- | --- |
| Name, one-line description, site URL | `_config.yml` (top) | `url` must be `https://<github-username>.github.io` |
| Headshot | `assets/img/prof_pic.jpg` | Square, at least 400×400. Keep the file name. |
| Title line, location, bio | `_pages/about.md` | |
| Social and contact links | `_data/socials.yml` | Delete the lines you don't use. |
| CV | `_pages/cv.md` | For now it asks visitors to email for the full resume. To post a PDF again: add `assets/pdf/cv.pdf`, link it on that page, and add `cv_pdf: /assets/pdf/cv.pdf` to `_data/socials.yml`. |
| Papers | `_bibliography/papers.bib` | One BibTeX entry per paper. The header comment lists the extra fields (video, pdf, code, preview, selected). |
| Paper PDFs | `assets/pdf/` | Then `pdf = {file.pdf}` in the entry, or use an arXiv URL. |
| Paper teaser images | `assets/img/publication_preview/` | About 600–800 px wide. Then `preview = {file.png}`. |
| Paper videos | `assets/video/` | MP4 (H.264), under 50 MB each; GitHub rejects files over 100 MB. Then `video = {/assets/video/name.mp4}` in the entry. The Video button plays it on the page. |
| Projects and previous work | `_projects/*.md` | Copy an example file. `category:` is `research` or `industry`. |
| Project images | `assets/img/projects/` | |
| News items | `_news/YYYY-MM-DD-short-name.md` | Copy the existing one. The 5 newest show on the home page. |

Keep the repo under 1 GB (the GitHub Pages limit). The deploy copies the built site to a `gh-pages` branch, so every video is stored twice. Resize photos to about 1600 px on the long side, and compress videos before adding them:

```bash
ffmpeg -i input.mov -vf "scale='min(1280,iw)':-2" -c:v libx264 -crf 26 -preset slow -c:a aac -b:a 96k -movflags +faststart assets/video/name.mp4
```

`assets/js/common.js` is a local copy of the theme's script with a fix for the paper Video button. After a theme upgrade, check whether it is still needed.

## Preview locally

Needs Docker. From this folder:

```bash
bin/preview
```

Then open <http://localhost:8080>. Edits to content files show up on refresh. After editing `_config.yml`, stop it with Ctrl-C and run it again.

## Publish (first time)

1. On GitHub, create a **public** repo named exactly `<github-username>.github.io`. Leave it empty.
2. Set `url` in `_config.yml` to `https://<github-username>.github.io`.
3. Push this folder to it:
   ```bash
   git remote add origin git@github.com:<github-username>/<github-username>.github.io.git
   git add -A && git commit -m "First version of my website"
   git push -u origin main
   ```
4. Repo **Settings → Actions → General → Workflow permissions**: choose **Read and write permissions** and save.
5. Wait for the **Deploy site** workflow in the **Actions** tab to finish (about 4 minutes). It builds the site into the `gh-pages` branch.
6. **Settings → Pages → Build and deployment**: Source **Deploy from a branch**, branch **gh-pages**, folder **/ (root)**.
7. After a minute the site is live at `https://<github-username>.github.io`.

## Update later

Edit the files above, commit and push to `main`. The deploy workflow rebuilds the site.

## Optional

- **Custom domain** (about $10–15/year): buy it from a registrar, add it under **Settings → Pages → Custom domain**, and set `url` in `_config.yml` to it.
- **More features** (blog, structured HTML CV, citation counts, analytics): see the [al-folio docs](https://github.com/alshedivat/al-folio/tree/main/docs). The demo content for them was removed from this copy.
