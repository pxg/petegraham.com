# AGENTS.md

## Cursor Cloud specific instructions

This is a Jekyll static blog site (petegraham.com). See `README.md` for full development setup options.

### Running the dev server

```
bundle exec jekyll serve --host 0.0.0.0 --port 4000
```

The site will be available at `http://localhost:4000`. Jekyll watches for file changes and auto-regenerates.

### Build

```
bundle exec jekyll build
```

Output goes to `_site/`.

### Notes

- There is no linter or automated test suite configured for this project.
- No `Gemfile.lock` is committed; `bundle install` resolves dependencies fresh each time.
- The `github-pages` gem pins Jekyll to v3.9.x and includes all GitHub Pages plugins.
- `_config.yml` has `future: true`, so posts with future dates will render in development.
- System dependencies required: `ruby-full`, `build-essential`, `zlib1g-dev` (Ubuntu/Debian).
