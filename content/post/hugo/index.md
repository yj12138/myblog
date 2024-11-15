+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title = 'Hugo'
+++

# Install

- windows

```bash
set CGO_ENABLED=1
go install -tags extended github.com/gohugoio/hugo@latest
```

# Hugo Usage

## Create Project

```bash
hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
```

## Content

- posts

```bash
hugo new content content/posts/my-first-post.md
```

# Run

```bash
hugo server
hugo server -D # show draft
```

# Help Link

[Hugo Website](https://gohugo.io/)  
[Hugo Doc Website](https://gohugo.io/documentation/)
