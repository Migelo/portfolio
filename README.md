# mihac.de

[![deploy](https://github.com/Migelo/portfolio/actions/workflows/deploy.yml/badge.svg)](https://github.com/Migelo/portfolio/actions/workflows/deploy.yml)

Source of my personal website, [mihac.de](https://mihac.de). It is a [Jekyll](https://jekyllrb.com/) site based on the [al-folio](https://github.com/alshedivat/al-folio) theme, built by GitHub Actions and served from my own server.

## What is on the site

**[About](https://mihac.de/)** — the homepage. I am Miha Cernetic, a Kernel Engineer at [Cerebras Systems](https://www.cerebras.ai/) in Berlin since May 2026. Before that I was a postdoc with Damiano Caprioli at the University of Chicago working on hybrid PIC simulations, and I did my PhD at the Max Planck Institute for Astrophysics in Garching with Volker Springel on turbulence, high-order numerical methods, GPU computing and galaxy formation. Earlier: an MSc in Astrophysics at MPS Göttingen (radiative transfer in stellar atmospheres) and a BSc in Physics in Ljubljana (CMB anisotropies). The common thread is squeezing physics out of the largest machines available. The page also links the services I self-host — a [speedtest](https://fast.mihac.de/), a [privatebin](https://privatebin.mihac.de/), [file sending](https://send.mihac.de/) and [pairdrop](https://pairdrop.mihac.de/) — plus the running, cycling and climbing that happen when the servers behave.

**[Publications](https://mihac.de/publications/)** — generated from `_bibliography/papers.bib` by `jekyll-scholar`.

**[Repositories](https://mihac.de/repositories/)** — my GitHub profile stats and a card per repository, each with a one-line description. The list lives in `_data/repositories.yml`.

**[CV](https://mihac.de/cv/)** — serves `assets/pdf/cv.pdf`.

## Layout

| Path | Contents |
| --- | --- |
| `_pages/` | the about page and the publications, repositories and cv pages |
| `_bibliography/papers.bib` | the publication list |
| `_data/repositories.yml` | GitHub users and repos shown on `/repositories/` |
| `_layouts/`, `_includes/`, `_sass/` | theme templates and styles |
| `assets/` | images, PDFs, JS and CSS |
| `_config.yml` | site settings, plugins, analytics |

## Running it locally

```bash
bundle install
pip install jupyter
bundle exec jekyll serve --lsi
```

Or in Docker, which builds the image from the `Dockerfile` in this repo:

```bash
docker compose up --build
```

The site is then at `http://localhost:8080`. `pre-commit install` sets up the whitespace and YAML hooks in `.pre-commit-config.yaml`.

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the site with `jekyll build --lsi`, strips unused CSS with `purgecss`, copies `_site/` to the server over scp, and restarts the nginx container there. Pull requests build but do not deploy. Traffic is measured with a self-hosted Matomo at `visitors.mihac.de`.

## Credits

Built on [al-folio](https://github.com/alshedivat/al-folio) by Maruan Alshedivat and contributors, which in turn came from the [*folio](https://github.com/bogoli/-folio) theme by Lia Bogoev. Available under the [MIT License](LICENSE).
