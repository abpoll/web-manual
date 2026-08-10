# Pollack Group Lab Manual

This repository stores the lab manual for the Pollack Group in the School of Earth, Environment, and Sustainability at the University of Iowa. The manual details procedures and expectations for all lab members. It also includes quickstart guides for common lab tasks. 

All lab and community members are welcome to view the manual, make comments, and propose changes. 

## Instructions on Contributing to the Lab Manual

The lab manual is built with [Quarto](https://quarto.org/) and maintained through GitHub. Contributions are welcome, including corrections, clarifications, new documentation, and new cookbook recipes.

### Small changes

For minor corrections or edits, the easiest approach is to use the **Edit this page** link on the manual website. 

You can also use **Report an issue** to suggest a change without editing the documentation yourself.

### Larger changes

For new pages, substantial revisions, or changes that should be previewed locally:

1. Clone the repository.

   ```bash
   git clone git@github.com:abpoll/web-manual.git
   cd web-manual
   ```

2. Create a new branch.

   ```bash
   git switch -c descriptive-branch-name
   ```

3. Install the project's Python environment with [Pixi](https://pixi.sh/).

   ```bash
   pixi install
   ```

   Quarto itself is not managed by this environment and should be installed separately on your computer.

4. Preview the manual locally.

   ```bash
   quarto preview
   ```

5. Make your changes and confirm that the site renders correctly.

6. Commit and push your branch.

   ```bash
   git add .
   git commit -m "Describe your changes"
   git push -u origin descriptive-branch-name
   ```

7. Open a pull request on GitHub.

Please do not make substantive changes directly on the `main` branch. Pull requests allow changes to be reviewed and discussed before they become part of the manual.

### Python and executable documents

The manual's Python environment is defined by `pyproject.toml` and `pixi.lock`. Python code used in executable Quarto documents and general-purpose tutorials should use this environment unless the documentation specifically demonstrates another computing environment.

If a contribution requires an additional Python package, add it through Pixi rather than installing it manually:

```bash
pixi add package-name
```

Both `pyproject.toml` and the resulting `pixi.lock` changes should be included in the pull request.

### Contributing to the Guide

The [Guide](docs/guide/index.qmd) contains explanatory material about how the lab works, including our approaches to research computing, data analysis, scientific communication, and other aspects of research practice.

Changes and additions to the Guide are welcome through pull requests. For substantial new material, consider opening an issue first so that the scope and location of the material can be discussed before drafting.

### Contributing a Cookbook recipe

The [Lab Cookbook](docs/cookbook/index.qmd) contains short, task-oriented recipes for recurring lab workflows. Each recipe has its own `.qmd` file and follows a common structure so that procedures are easy to find, use, and maintain.

If you have an idea for a new recipe, **start by opening a GitHub issue**. The issue can be used to:

- describe the task or problem the recipe should address;
- determine whether an existing recipe already covers it;
- discuss where the recipe belongs in the Cookbook hierarchy;
- identify useful categories and metadata;
- identify related Guide pages and recipes; and
- coordinate with other lab members who may want to contribute.

Once the scope is clear, create the recipe on a branch and submit it as a **pull request**. Recipes should generally enter the manual through pull requests rather than being added directly to `main`. This gives other lab members an opportunity to test the procedure, suggest improvements, and verify that the instructions work outside the author's own setup.

When writing a recipe:

- follow the standard [recipe template](docs/cookbook/RECIPE_TEMPLATE.qmd);
- choose the most appropriate Cookbook section;
- add relevant categories to the page metadata;
- provide concrete, reproducible steps;
- include a way to verify that the procedure worked;
- document common errors or failure modes when useful; and
- link to relevant Guide pages and related recipes.

The goal is to maintain **one canonical recipe for each recurring workflow**. Guide pages should link to relevant recipes rather than duplicate their step-by-step instructions.

### Documentation style

Write for a lab member who may be encountering the topic for the first time. Prefer precise, reproducible instructions over assumptions about prior knowledge.

As a general rule:

- the **[Guide](docs/guide/index.qmd)** explains concepts, practices, and why we do things a particular way;
- the **[Cookbook](docs/cookbook/index.qmd)** explains how to accomplish specific tasks.

When possible, link between the two. A Guide page can point readers to recipes for implementation, while a recipe can point readers to the Guide for background and context.