# Huang Qiming's personal website

Live site: <https://ceilingfan456.github.io/huang-qiming/>

Repository: <https://github.com/ceilingFan456/huang-qiming>

A small academic website with a profile sidebar, introduction, publications,
and an online CV. The layout is inspired by [Ziyi Yang's website](https://ziyi510.github.io/).
The site uses plain HTML and CSS, with no build step or package installation.

## Preview locally

Double-click `index.html`, or run this from the repository folder:

```powershell
python -m http.server 8000 --bind 127.0.0.1
```

Then open <http://127.0.0.1:8000>. Stop the server with Ctrl+C.

## Update the content

| File | Content |
| --- | --- |
| `index.html` | Biography and research interests |
| `publications.html` | Public papers, author lists, venues, and links |
| `cv.html` | Education, experience, and research interests |
| `assets/profile.jpg` | Avatar from the supplied Google Scholar profile |
| `assets/style.css` | Shared colors, spacing, and responsive layout |
| `files/` | Optional public CV PDF or other downloads |

The profile sidebar, navigation, and footer are repeated in all three HTML files
so the site works without JavaScript or a build system. Keep these sections in sync.
To add a paper, copy an existing `article` in `publications.html` and update its
contents. To add a PDF CV later, see `files/README.md`.

The GitHub account is `ceilingFan456`; the repository is `huang-qiming`. Therefore
the current site is a project site at `/huang-qiming/`. Relative links allow all
pages and assets to work at this address, locally, or at a future personal-site root.

## Publish updates

From this folder:

```powershell
git add index.html publications.html cv.html assets README.md files
git commit -m "Update personal website"
git push origin main
```

GitHub Pages is configured to publish `main` from `/ (root)`. Keep the custom-domain
field empty when using the default GitHub Pages address. The `.nojekyll` file
allows the static site to be served without Jekyll processing.

Check deployment progress in the repository's
[Actions tab](https://github.com/ceilingFan456/huang-qiming/actions).

## Content sources

Profile details were checked on 28 September 2026 against the supplied
[Google Scholar](https://scholar.google.com/citations?user=-xfbAA4AAAAJ&hl=en) and
[OpenReview](https://openreview.net/profile?id=~Huang_Qiming1) profiles.
The online CV uses the education dates and role titles listed there; degree
specializations and a PDF CV have not been supplied.

Paper titles and author order follow the public papers. Venue information is
included where publicly confirmed:

- [RobotSeg](https://arxiv.org/abs/2511.22950), with CVPR 2026 oral status confirmed
  by the [project repository](https://github.com/showlab/RobotSeg).
- [Show-Harness](https://arxiv.org/abs/2609.10522), with its
  [public project page](https://showlab.github.io/Show-Harness/).
- [Supervise What Survives](https://arxiv.org/abs/2606.24448).

For deployment details, see the
[GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).
