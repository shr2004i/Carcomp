# Your EV decision, simplified.

A responsive, interactive EV comparison for a family buying in Bhubaneswar, Odisha, with a ₹24 lakh on-road budget. Includes the latest dark-blue design and red accents.

The website is a single self-contained HTML file. It requires no build, npm packages, API keys, database or backend. It can run from GitHub Pages, another static host, or by opening `index.html` in a browser.

## Included files

| File | Purpose |
| --- | --- |
| `index.html` | Complete website, inline CSS, JavaScript and comparison data |
| `.github/workflows/deploy.yml` | Deploys to GitHub Pages after pushes to `main`, or manually |
| `.nojekyll` | Marks the website as plain static files |
| `.gitignore` | Excludes local OS files and temporary deployment output |
| `README.md` | Setup, deployment and editing instructions |

## Deploy on GitHub Pages

1. Extract the ZIP. Open the `bhubaneswar-ev-github` folder.
2. Create a GitHub repository. A public repository works with GitHub Free; private-repository Pages support depends on your GitHub plan.
3. Upload **the contents of this folder** to the repository root and commit to `main`. Upload the extracted files, not the ZIP. Keep `.github/workflows/deploy.yml` and the other dotfiles.
4. In the repository, open **Settings → Pages → Build and deployment**. Set **Source** to **GitHub Actions**. The included workflow is already configured; do not generate a second workflow.
5. Open **Actions → Deploy to GitHub Pages → Run workflow** and choose `main`. Once it succeeds, open the deployment URL shown in the run or in **Settings → Pages**.

Future pushes to `main` deploy automatically. No personal access token or repository secret is needed; the workflow uses GitHub's built-in token.

GitHub Pages serves the site without the ChatGPT sign-in gate used by the earlier hosted version. The site itself has no login system. Standard GitHub Pages sites are publicly accessible.

### Optional: upload with Git

Create an empty repository first. From inside the extracted project folder, run the following commands. Replace `YOUR-USERNAME` and `YOUR-REPO` with your GitHub account and repository name.

```bash
git init
git add .
git commit -m "Add EV comparison website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

Then complete steps 4–5 above. On macOS, **Command + Shift + .** shows hidden files in Finder if you are uploading through the browser. Using `git add .` includes them automatically.

## Edit the website

- **Comparison data:** find `const DATA = {` near the top of the inline script in `index.html`. It contains cars, trims, prices, range, warranties, scores, costs, footnotes and sources.
- **Numbers:** some entries have a visible string plus a numeric counterpart, such as `price` and `priceValue`, or `cost8` and `cost8Value`. Keep both consistent when editing. Numeric counterparts control highlights and chart widths; totals are not recalculated.
- **Design:** CSS is inside the `<style>` block. Palette variables are in `:root`; the red accent overrides are labelled `Restrained red accents`.
- **Behaviour:** vanilla JavaScript follows the `DATA` object. Checklist state is temporary; the app does not use browser storage.
- **Add separate assets later:** also update the workflow's copy step to include those files. The supplied site needs only `index.html`.

Opening `index.html` directly is enough for local preview. The complete site works under a GitHub project subpath because it uses inline assets and page-local anchor links.

## Troubleshooting

| Issue | Check |
| --- | --- |
| Initial deployment fails before Pages is enabled | Choose GitHub Actions in Pages settings, then run the included workflow again. |
| Workflow is missing from Actions | Confirm `.github/workflows/deploy.yml` was uploaded at the repository root. |
| Homepage is missing | Confirm `index.html` is at the repository root, not inside an extra wrapper folder. |
| Pushes do not deploy | The workflow watches `main`. Change the branch name in `deploy.yml` if needed. |
| Pages settings are unavailable | Check repository permissions, visibility and GitHub plan support. |

## Report snapshot

The supplied report snapshot is dated **27 October 2026**. This package preserves its figures, estimate labels, sources and recommendations. It is not a live pricing feed. On-road prices are estimates, not dealer quotations; obtain written quotes before purchasing.

## Official deployment references

- [Using custom workflows with GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)
- [Configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
