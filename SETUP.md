# Publish your GitHub profile README

This is a **GitHub profile README**, not a standalone web app. It appears on your GitHub profile when you upload the files to the special repository matching your username.

## 1. Create the special profile repository

1. Log into [GitHub](https://github.com/new).
2. Set the repository name to exactly **`sidharthWadhwa726`**.
3. Select **Public**. Check **Add a README file** if prompted.
4. Create the repository.

> If that repository already exists, open it instead. The repository must be public and have `README.md` in its root.

## 2. Upload the contents of this ZIP

Upload `README.md`, the complete `assets/` folder, and optionally the `.github/workflows/` folder to the **root of the profile repository**. Do not upload the parent folder itself.

On GitHub: **Add file → Upload files → Commit changes**. Upload the `assets` folder with its SVGs (all files). GitHub's web uploader handles dragging whole directories on desktop; alternatively push with Git (below).

With PowerShell in this extracted folder, if the remote repository is empty or newly initialized:

```powershell
git init
git branch -M main
git add README.md assets .github SETUP.md
git commit -m "Create Obsidian GitHub profile"
git remote add origin https://github.com/sidharthWadhwa726/sidharthWadhwa726.git
git push -u origin main
```

If the remote already has a `README.md`, clone it first and copy these files into that cloned directory rather than pushing an unrelated local history.

## 3. Verify

Visit **https://github.com/sidharthWadhwa726**. The custom header and project cards should be rendered above the regular repositories section.

If you see broken images, verify all SVGs are located under `assets/` with the exact filenames included here.

## 4. Optional: contribution snake

The ZIP includes `.github/workflows/snake.yml` that can generate an animated contribution snake without using a public third-party image endpoint.

To enable it:

1. Upload the workflow file to `.github/workflows/snake.yml` in the profile repository.
2. In GitHub **Settings → Actions → General → Workflow permissions**, select **Read and write permissions** if your account/repository allows it. Save.
3. Open **Actions → Generate contribution snake → Run workflow**. Allow the initial run to finish and create an `output` branch.
4. Edit `README.md`: remove the `<!--` and `-->` markers around the snake `<p>...</p>` block in the `GitHub activity` section.
5. Commit the README edit. The snake URL then loads from your own repository's `output` branch.

The animation will update daily once the scheduled GitHub Action runs. GitHub Actions and repository permissions can change; if the workflow fails, inspect its run logs before enabling the image link.

## 5. Customize when ready

- **PrepForge:** its URL `https://github.com/sidharthWadhwa726/PrepForge` currently returned HTTP 404 to a public visitor when this file was prepared. Once it becomes public, add a source link to its project mention.
- **Portfolio website:** deploy the Obsidian AI Studio site to Vercel; then add the real deployed URL under the header links.
- **Résumé:** a PDF was intentionally not copied to this public repository, since your existing résumés contain personal contact details. You can add a public, phone-free version if you want a resume link.
- **GitHub bio:** replace the older 'undergrad ... CP, AI/ML' sentence with something role-oriented, e.g. `Software engineering · Applied AI · Backend | Building RAG systems & data-driven products | IIT Jammu '28`.
- **Pinned repositories:** Pin your GitHub Repository Analyzer and Real_Time_System_Monitor; add B2SCVR and the Solar Burst project if eligible. Forks might not be pinnable under GitHub's current rules without qualifying contributions.
- **Achievements:** this README uses the numerical claims in your uploaded résumé; update them as they change.

## About visual compatibility

GitHub profile READMEs allow Markdown and a safe subset of HTML. JavaScript and custom CSS do not run. The design uses original, static SVG images plus ordinary Markdown for a polished result that is compatible with GitHub's renderer. The optional snake is a separate generated SVG animation and may not play in every environment.
