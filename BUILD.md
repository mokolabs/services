# How to build the docs

The documentation site at [mokolabs.github.io/services](https://mokolabs.github.io/services/) is auto-generated from `README.md`.

## Prerequisites

- Ruby (via rbenv and the like)
- Bundler (`gem install bundler`)
- Run `bundle install` to install dependencies

## Generating the docs

After editing `README.md`, regenerate the HTML:

```
bin/build
```

This reads `README.md` and generates `docs/index.html`.

## Previewing locally

```
foreman start -f Procfile.dev
```

Then open [http://localhost:3000](http://localhost:3000).

## Deploying

Push to `main`. GitHub Pages automatically deploys from the `docs/` directory.
