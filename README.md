[Website](https://www.floydhub.com) • [Docs](https://docs.floydhub.com) • [Forum](https://forum.floydhub.com) • [Twitter](https://twitter.com/floydhub_) • [We're Hiring](https://angel.co/floydhub)

[![FloydHub Logo](https://github.com/floydhub/static/blob/master/Group.png)](https://www.floydhub.com)

# FloydHub Documentation
This code generates FloydHub's documentation: [http://docs.floydhub.com/](http://docs.floydhub.com/).

## Contributing
Please feel free to make pull requests or file issues if you think there's anything missing or if there's something we should explain more clearly. We love pull requests!

### Running docs locally
* Install requirements.txt with `pip install -r requirements.txt`
* Use `mkdocs serve` to run a local server and build/preview documentation. You can view the docs at [ http://127.0.0.1:8000]( http://127.0.0.1:8000)
* To build the static site, use `mkdocs build`. This step is not necessary if hosting the site on Github Pages (which is what is currently done)

### Steps to deploy (only admins)
Any pushes or merges to master will deploy to Netlify automatically.
