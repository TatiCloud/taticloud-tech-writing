# Welcome to TatiCloud Documentation Hub

Welcome! This site is a growing collection of practical notes for people working with **cloud computing** and the **Linux terminal**. Everything here comes from real hands-on work, such as maintaining servers, fixing problems, and writing down what worked so it can be repeated.

For the main website, visit [taticloud.com](https://www.taticloud.com).

## Introduction

- **Linux commands for cloud computing**: checking memory, disk space, and logs, managing swap, and keeping a cloud server healthy.
- **Linux Terminal commands you can copy and use**: short, tested examples with a note on what each one does.
- **How to write tech docs**: creating clear documentation with Markdown and MkDocs.
- **How to publish your docs**: building them locally and pushing them to Git so they're available online.


## Quick start: create your own docs

**1. Install MkDocs and create a project**

```bash
pip install mkdocs
mkdocs new my-docs
cd my-docs
```

**2. Write in Markdown**

Add pages as `.md` files in the `docs/` folder and list them in `mkdocs.yml`:

```yaml
site_name: My Docs
nav:
  - Home: index.md
  - Check Free Memory: check-memory.md
```

**3. Preview locally**

```bash
mkdocs serve
```

Open <http://127.0.0.1:8000>. The page reloads each time you save.

**4. Push your docs to Git**

```bash
git init
git add .
git commit -m "First version of docs"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/my-docs.git
git push -u origin main
```

**5. Publish the site**

```bash
mkdocs gh-deploy
```

Your site will be available at `https://YOUR-USERNAME.github.io/my-docs/`.

## Good practices

- Keep one topic per page, with commands in code blocks.
- Never publish passwords, tokens, or server IP addresses.
- Test commands before documenting them, and note anything that needs `sudo`.

Happy documenting!
