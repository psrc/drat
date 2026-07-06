
## `drat` Repository for easy forking

`drat` ([CRAN](https://cran.r-project.org/package=drat), [GitHub](https://github.com/eddelbuettel/drat), [docs](https://eddelbuettel.github.io/drat)) makes it easy to host your own
CRAN-like repositories for packages (or [data](https://journal.r-project.org/archive/2017/RJ-2017-026/index.html)).

Many users have started their own `drat` repo by forking the original [GitHub
repo](https://github.com/eddelbuettel/drat) -- but as time passes this _code_ repo
accumulates more _code_ for `drat`, as well as
[documentation](https://eddelbuettel.github.io/drat)
 making it less of an ideal place to start for _your own_ repo.  So this repo offers an alternative:

- Just fork this repo into your own domain, and you have a working `drat`
 repo.
- Enable [GitHub Pages](https://docs.github.com/en/github/working-with-github-pages)
	from the `gh-pages` branch at the repository root (`/`):

 ![](https://github.blog/wp-content/uploads/2016/08/47c2ecc4-6533-11e6-828a-91980daa7297.gif)

For this repository, the published site and package index should live on
`gh-pages` at `/`, which is the default `drat` publishing layout.

The `docs/` directory in the source branch remains the staging area for the
published repository contents; a deploy workflow can copy `docs/` to the root
of `gh-pages`.

This repo was initiated (using command `dratPackage()`) with the source and
windows binary of the last CRAN release of `drat`. You can delete either or
both (for example via command `pruneRepo()`) and then
add your own (via `insertPackage()`).

### Deployment

The expected deployment flow is:

1. Build or obtain package artifacts for the PSRC packages.
2. Add source tarballs under `docs/src/contrib/` and Windows binaries under
	`docs/bin/windows/contrib/4.0/`.
3. Regenerate the `PACKAGES` metadata in `docs/`.
4. Publish the contents of `docs/` to the root of the `gh-pages` branch.

### Author

Dirk Eddelbuettel

### License

GPL (>= 2)
