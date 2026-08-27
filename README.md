# Yuxi Hong — academic website

Source for [hongyx11.github.io](https://hongyx11.github.io), built with Jekyll and the Academic Pages template.

## Add an HPC Starter article

Create a Markdown file in `_posts` named `YYYY-MM-DD-short-title.md`. Include front matter with `title`, `date`, `permalink`, `tags`, and `excerpt`, then link the lesson from `_pages/hpc-starter.md` if it belongs in the structured path.

## Preview locally

```bash
bundle install
bundle exec jekyll serve
```

The site is deployed automatically from the `main` branch with GitHub Actions.
