# Personal academic website

A small, responsive personal website with a profile sidebar, an introduction,
a publications page, and a CV page. The layout is inspired by
[Ziyi Yang's website](https://ziyi510.github.io/); the implementation and graphics
here are original. No framework, JavaScript, package installation, or build step
is required.

## Preview

Double-click `index.html` to open the site in your browser. All pages and assets
use relative links, so they also work directly from your local folder.

Alternatively, run this in PowerShell from the `personal-page` folder:

```powershell
python -m http.server 8000 --bind 127.0.0.1
```

Open <http://127.0.0.1:8000>. Press Ctrl+C in the terminal to stop the server.

## Make it yours

| File | What to edit |
| --- | --- |
| `index.html` | Your introduction and research interests |
| `publications.html` | Your papers; a reusable entry is included in an HTML comment |
| `cv.html` | Your education, experience, and optional PDF link |
| `assets/style.css` | Colors, spacing, and layout |
| `assets/profile.svg` | The placeholder portrait; replace it with your own image |
| `files/` | Your public CV and other downloadable files |

1. Replace `Your Name` in all three HTML files, including page titles, descriptions,
   navigation, profile, and footer.
2. Replace or remove every bracketed placeholder. The three pages deliberately
   keep their own small profile section so the site works without a build system
   or JavaScript. Make profile edits in all three files.
3. Save your photo as `assets/profile.jpg`, then change `src="assets/profile.svg"`
   to `src="assets/profile.jpg"` in each HTML file. Change the image `alt` to your name.
4. In each profile section, fill in the contact URLs and remove the surrounding
   `<!-- ... -->` comment to display the links. Delete any links you do not want.
5. Add papers using the commented example in `publications.html`. Replace the example
   URLs and remove the empty-state paragraph when you add your first paper.
6. Save your CV as `files/CV.pdf`, enable the commented download link in `cv.html`,
   and remove the "available here soon" paragraph. To open the PDF directly from
   navigation, change the CV links in all three pages to `files/CV.pdf`.

Search for `EDIT:`, `Your Name`, and `[` to find the areas to personalize.
There are no invented papers or credentials, and example external links stay
hidden until you enable them.

## Publish as your GitHub personal page

Git is already initialized locally on the `main` branch. There is no remote or
commit yet; the first commit below will use your own Git author identity.
Replace `YOUR_USERNAME` with your GitHub username everywhere below.

### 1. Create an empty repository on GitHub

Go to <https://github.com/new> and create a **public** repository named exactly:

```text
YOUR_USERNAME.github.io
```

For this existing local project, leave the options to add a README, `.gitignore`,
or license **off**, so the remote starts empty. The local folder may stay named
`personal-page`; only the GitHub repository needs the special name.

### 2. Commit and push this folder

Open PowerShell in the `personal-page` folder. Set the author identity for this
repository, using your name and an email listed in GitHub Settings > Emails
(you can use the private `noreply` address shown there):

```powershell
git config user.name "YOUR NAME"
git config user.email "YOUR GITHUB EMAIL"
git add .
git commit -m "Create personal website"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_USERNAME.github.io.git
git push -u origin main
```

Complete GitHub sign-in if Git prompts you. These `git config` commands affect
only this repository. If `origin` already exists, inspect it with `git remote -v`
and use `git remote set-url origin <correct-repository-url>` to correct it.

### 3. Enable GitHub Pages

In the GitHub repository, open **Settings > Pages**. Under **Build and deployment**:

- **Source:** Deploy from a branch
- **Branch:** `main`
- **Folder:** `/ (root)`

Click **Save**. Once deployment finishes, your site will be at:

```text
https://YOUR_USERNAME.github.io/
```

Publishing can take up to 10 minutes. You can check the deployment in the
repository's **Actions** tab. The `.nojekyll` file tells Pages to serve the static
site without Jekyll processing; no custom workflow is necessary.

### 4. Update your page later

Edit the files, preview locally, then run:

```powershell
git add .
git commit -m "Update personal website"
git push
```

GitHub Pages will publish the update automatically.

Official instructions:
[GitHub Pages quickstart](https://docs.github.com/en/pages/quickstart) and
[configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).
