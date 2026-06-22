# Customize This Site

This site is based on the open-source [al-folio](https://github.com/alshedivat/al-folio) template.

## Replace These First

- `_config.yml`
  - `first_name`, `last_name`
  - `url`
  - `baseurl`
  - `description`
- `_pages/about.md`
  - homepage subtitle
  - short bio
  - profile contact text
- `_projects/*.md`
  - project titles, descriptions, categories, images, and links
- `_data/repositories.yml`
  - add `github_users` and `github_repos` when public GitHub links are ready
- `_data/socials.yml`
  - email and social usernames

## Deployment Choice

For this user site, keep:

```yml
url: https://Chubbyemo.github.io
baseurl: ""
```

For a project repository such as `personal-site`, use:

```yml
url: https://Chubbyemo.github.io
baseurl: /personal-site
```
