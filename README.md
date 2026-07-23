# inayi.github.io

Personal website of Ina Yi, built with [Jekyll](https://jekyllrb.com/) and the [minima](https://github.com/jekyll/minima) theme, hosted on GitHub Pages.

## Running locally

```sh
bundle install          # install dependencies (once)
bundle exec jekyll serve # serve at http://localhost:4000
```

## Structure

- `index.markdown` — homepage (lists blog posts)
- `about.markdown` — About page
- `_posts/` — blog posts
- `projects.markdown` — Projects page
- `_data/projects.yml` — project entries shown on the Projects page
- `_config.yml` — site configuration

## Adding a project

Edit `_data/projects.yml` and add a block:

```yaml
- title: My New Project
  status: idea          # idea | planning | in-progress | done
  description: What it is.
  link: https://...     # optional
  tags: [tag1, tag2]    # optional
```
