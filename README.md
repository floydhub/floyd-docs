# floyd-docs
FloydHub Documentation

## Steps to build and deploy documentation
* Install `mkdocs`
* Use `mkdocs serve` to run a local server and build/preview documentation
* To build the static site, use `mkdocs build`. This step is not necessary if hosting the site on Github Pages (which is what is currently done)
* To deploy static site to gh-pages, run `mkdocs gh-deploy`. This will build the static site, commit it to the gh-pages branch and push the branch to Github
