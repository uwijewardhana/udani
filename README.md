Repository for my [personal webpage](https://uwijewardhana.github.io), built using the `R` package `blogdown` and the [academic theme](https://sourcethemes.com/academic/)

Resources used to built this webpage
 - [`blogdown` book](https://bookdown.org/yihui/blogdown/)
 - [academic documentation](https://sourcethemes.com/academic/docs/get-started/)
 - [deploying site to GitHub](https://richardlent.github.io/post/how-i-deploy-my-website-to-github-using-rstudio-blogdown-and-hugo/)

In brief, to build a similar webpage

 1. Install the `R` package `blogdown` and download/deploy a new site with the academic theme
 `blogdown::new_site(theme = "gcushen/hugo-academic")` into an empty directory.
 2. Run `blogdown::serve_site()` and the site will open in your browser.
 3. Personalise
    - Edit `content/authors/adim/_index.md` as appropriate and add a bio picture `avatar.jpg/png` in the same directory.
    - In `content/home` edit the relevant `.md` files as required and delete those not needed. The weight specified in each file will dictate the ordering of the sections (higher weight the lower down the section).
    - The `page_type` specified in the`.md` files in `content/home` should refer to a directory in `content/` (e.g., `projects.md` should specify `page_type = "project"` and therefore `project/` should be a directory in `content/`).
    - Each linked directory (as `project/` above) should contain named sub directories each with two files: `index.md` and `featured.png/jpg`. The `index.md` files should give a brief description of the project etc. The image `featured.png/jpg` will be displayed with this information in the relevant section on your webpage.
    - To change the ordering or menu text edit the `config/_default/menues.toml` file. Here again the specified `weight` dictates ordering and the `url` for each link should point to the relevant filename in `content/home`.
    - To change the icon in the tab change the icons in `static/img`.
    - Other changes can be made to `config.toml` to change layout; see [here]((https://sourcethemes.com/academic/docs/get-started/)) for more advanced options.

 4. To deploy on GitHub I set `baseurl = "https:///uwijewardhana.github.io"` and added `publishDir = "..//uwijewardhana.github.io"` into `config.toml` (don't forget to change `uwijewardhana` to your own GitHub handle!). The former is the web address the webpage will be deployed to and the latter is telling `blogdown` to write the static files to the directory "..//uwijewardhana.github.io" (i.e., at the same level as the current directory) and not the default `public/` in the root of the folder. Then delete the `public/` folder and re run `blogdown::site_serve()`, check that things are as you expect/want. Now your static webpage files should have been written to `"../<yourGitHubhandle>.github.io"`. Moving into this directory git initialize it, git add & commit, and push to GitHub. Your site should now be available at `"https://<yourGitHubhandle>.github.io"`.
