# AI · Math · Science

Personal site built with [Hugo](https://gohugo.io/) and the
[hugo-PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

Live site: <https://mengyaozhu.github.io/>

## Content

- `content/posts/` — blog/posts
- `content/about.md`, `content/projects.md`, `content/archives.md`, `content/search.md` — static pages
- `layouts/` — custom templates and shortcodes (including the glossary feature)
- `assets/css/extended/` — custom CSS overrides

## Local development

Install [Hugo](https://gohugo.io/installation/) (extended, v0.161.1 to match the
build workflow), then:

```sh
hugo serve          # local preview at http://localhost:1313
hugo                # build into ./public
```

The site also ships a GitHub Actions workflow (`.github/workflows/deploy.yml`)
that builds with `hugo --minify` and deploys to GitHub Pages on every push to
`main`.

## Glossary feature

Posts can opt into a right-side term-definition panel:

- Put `{{< glossary >}}` at the top of a post.
- Wrap each term you want defined with:

  ```
  {{< term def="the definition text" id="a-unique-id" >}}**the phrase**{{< /term >}}
  ```

The panel is rendered by `layouts/shortcodes/glossary.html` and styled by
`glossary.css`. A scroll-tracking script highlights the term nearest the
reading line and aligns its definition on the right, then hides the panel once
you scroll past the last term.

See `content/posts/task-academic-reading-for-ai-qwen-3.5-omni-03.md` for a
working example.
