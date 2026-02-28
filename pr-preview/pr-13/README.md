# petegraham.co.uk

Code for petegraham.co.uk based on https://github.com/nickbalestra/kactus.

## Development Setup

### Option 1: Using Docker (Recommended)

1. Build the Docker image:
```
docker build -t pxg-blog .
```

2. Run the site locally:
```
docker run -p 4000:4000 -v $(pwd):/site pxg-blog bundle exec jekyll serve --host 0.0.0.0 --incremental --force_polling --livereload
```

This command:
- Mounts your local directory for immediate updates
- Enables incremental builds
- Includes live reload for automatic browser refresh
- Watches for file changes

The site will be available at `http://localhost:4000`

If you need a clean build:
1. Stop the server (Ctrl+C)
2. Delete the `_site` directory
3. Run the command again

### Option 2: Local Ruby Installation

You need Ruby 2.1.0 or higher installed for Jekyl with Github pages https://help.github.com/enterprise/2.11/user/articles/setting-up-your-github-pages-site-locally-with-jekyll/#step-1-create-a-local-repository-for-your-jekyll-site. OS X currently has Ruby 2.0 as it's built in version.

Install rvm https://rvm.io/rvm/install:
```
curl -sSL https://get.rvm.io | bash -s stable --ruby
```

Activate rvm:
```
source ~/.rvm/scripts/rvm
```

Install bundler:
```
gem install bundler
```

Install dependencies:
```
bundle install
```

## Running

```
rvm use 2.4.1
jekyll serve
```

## Deploying

Simply push to main:
```
git push
```

## PR preview workflow

This repository now includes two GitHub Actions workflows:

- `.github/workflows/deploy-pages.yml`  
  Builds Jekyll on pushes to `main` and deploys the generated `_site` to `gh-pages`.
- `.github/workflows/pr-preview.yml`  
  Builds a PR-specific preview and deploys it to `gh-pages/pr-preview/pr-<PR_NUMBER>/`, then comments the preview URL on the pull request.

### One-time GitHub settings

1. In **Settings → Pages**, set:
   - **Source**: `Deploy from branch`
   - **Branch**: `gh-pages`
   - **Folder**: `/ (root)`
2. In **Settings → Actions → General → Workflow permissions**, set:
   - **Read and write permissions**

Once enabled, preview links will follow:

`https://petegraham.com/pr-preview/pr-<PR_NUMBER>/`

> Note: preview deployment for forked pull requests is not supported by the current preview action configuration.