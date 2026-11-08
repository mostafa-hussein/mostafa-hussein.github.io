# Personal website

My research and portfolio site, built on the [al-folio](https://github.com/alshedivat/al-folio) Jekyll template and hosted free on GitHub Pages at <https://mostafa-hussein.github.io>.

Pages: **About** (home) · **Projects** · **Publications** · **CV** · News.

## Where everything goes

| What | File | Notes |
| --- | --- | --- |
| Name, one-line description, site URL | `_config.yml` (top) | `url` must be `https://<github-username>.github.io` |
| Headshot | `assets/img/prof_pic.jpg` | Head-and-shoulders crop, 4:5, about 640×800. Keep the file name. |
| Title line, intro, text under the photo | `_pages/about.md` | Keep the intro to two short paragraphs; the home page shows it next to the photo. |
| Home page structure | `_layouts/about.liquid` | Intro → featured projects → selected publications → recent news → contact. |
| Social and contact links | `_data/socials.yml` | Delete the lines you don't use. |
| Web CV | `_data/cv.yml` | Experience, education, skills, patents, selected publications. Rendered on `/cv/`. |
| PDF resume | `assets/pdf/Mostafa_Hussein_Resume.pdf` | Overwrite with the new file (keep the name). Keep `_data/cv.yml` in sync with it. |
| Papers | `_bibliography/papers.bib` | One BibTeX entry per paper. The header comment lists the extra fields (video, pdf, code, preview, selected). |
| Paper PDFs | `assets/pdf/` | Then `pdf = {file.pdf}` in the entry, or use an arXiv URL. |
| Paper teaser images | `assets/img/publication_preview/` | About 600–800 px wide. Then `preview = {file.png}`. |
| Paper videos | `assets/video/` | MP4 (H.264), under 50 MB each; GitHub rejects files over 100 MB. Then `video = {/assets/video/name.mp4}` in the entry. The Video button plays it on the page. |
| Projects and previous work | `_projects/*.md` | Copy an existing file. `category:` is `research` or `industry`; `featured: true` puts it on the home page (keep it to three). Sections: The problem, What I did, Results, Paper. |
| Project card images | `assets/img/projects/cards/` | 16:9, about 1200×675. Photos are cropped to fill; diagrams sit on white. Projects with no public image get a plain navy card with the title. |
| Project page figures | `assets/img/projects/` | |
| News items | `_news/YYYY-MM-DD-short-name.md` | Copy an existing one. The 4 newest show on the home page. |
| Colors | `assets/css/main.scss` | The accent blue and dark-mode blue are set at the top. Other site styles live in `_sass/_custom.scss`. |

Keep the repo under 1 GB (the GitHub Pages limit). The deploy copies the built site to a `gh-pages` branch, so every video is stored twice. Resize photos to about 1600 px on the long side, and compress videos before adding them:

```bash
ffmpeg -i input.mov -vf "scale='min(1280,iw)':-2" -c:v libx264 -crf 26 -preset slow -c:a aac -b:a 96k -movflags +faststart assets/video/name.mp4
```

Local copies of theme files, kept because they carry site-specific changes: `assets/js/common.js` (fix for the paper Video button), `assets/css/main.scss` (colors), `_layouts/about.liquid` (home page), `_layouts/cv.liquid` (download button). After a theme upgrade, compare them with the theme's versions.

## Preview locally

Needs Docker. From this folder:

```bash
bin/preview
```

Then open <http://localhost:8080>. Edits to content files show up on refresh. After editing `_config.yml`, stop it with Ctrl-C and run it again.

## Publish

Commit and push to `main`. The **Deploy site** workflow builds the site into the `gh-pages` branch, which GitHub Pages serves; it takes about 4 minutes. Pushing needs the `mostafa-hussein` GitHub account (`gh auth switch -u mostafa-hussein`).

## Optional

- **Custom domain** (about $10–15/year): buy it from a registrar, add it under **Settings → Pages → Custom domain**, and set `url` in `_config.yml` to it.
- **More features** (blog, citation counts, analytics): see the [al-folio docs](https://github.com/alshedivat/al-folio/tree/main/docs). The demo content for them was removed from this copy.
