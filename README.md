# FloydHub Documentation
This code generates FloydHub's documentation: [http://docs.floydhub.com/](http://docs.floydhub.com/). 

## Contributing
Please feel free to make pull requests, if there's anything you feel we could do better!

### Steps to build docs locally
* Install requirements.txt with `pip install -r requirements.txt`
* Use `mkdocs serve` to run a local server and build/preview documentation. You can view the docs at [ http://127.0.0.1:8000]( http://127.0.0.1:8000)
* To build the static site, use `mkdocs build`. This step is not necessary if hosting the site on Github Pages (which is what is currently done)

### Steps to deploy (only admins)
* To deploy static site to gh-pages, run `mkdocs gh-deploy`. This will build the static site, commit it to the gh-pages branch and push the branch to Github
