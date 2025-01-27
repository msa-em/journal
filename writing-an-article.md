---
title: Submit your Research
description: ''
short_title: ''
---


```{important}
The submission process currently requires communicating with an `EM` editor.
Please get in touch with [Colin](mailto:cophus@stanford.edu) or [George](mailto:gvarnavides@berkeley.edu) if you are interested in submitting an article for `Elemental Microscopy`.
```

These instructions will help you prepare and submit your manuscript using the EM platform. 
We give instructions for both advanced and beginning users, based on their familiarity with basic command-line tools, version control using Git, and working within a Python environment. 

The EM platform uses open-source technologies such as [MyST Markdown](https://mystmd.org/), [Jupyter Notebooks](https://jupyter.org/), and [conda](https://docs.conda.io/projects/conda/en/latest/index.html#)/[uv](https://docs.astral.sh/uv/) for environment management. 
Authors are encouraged to include interactive elements such as embedded code, multimedia (e.g., images, movies, 3D volumes), and datasets in their manuscripts. 
While advanced technical expertise is not required, familiarity with these tools will help you fully leverage the platform's capabilities. 
For new users, EM provides templates, documentation, and examples to guide you through the process. 
Please contact [Colin](mailto:cophus@stanford.edu) or [George](mailto:gvarnavides@berkeley.edu) if you need some help getting started!

---

## Advanced Users

### Step 1: Setting Up Your Environment

1. **Clone the Repository**
   - Fork the [EM Quickstart](https://github.com/msa-em/em-quickstart), [EM Template](https://github.com/msa-em/em-template), or another EM article from [GitHub](https://github.com/msa-em) and give it a descriptive name.
   - Clone your fork:  
     ```
     git clone git@github.com:<your-git-handle>/<your-repo-name>.git
     ```
   - Switch to the `dev` branch:  
     ```
     git checkout -b dev
     ```

2. **Configure the Environment**
   - Edit the `environment.yml` file:
     - Change the environment name to match your repository name.
     - Add any required Python package dependencies, pinning versions as needed.
   - Create the virtual environment:  
     ```
     conda env create -f environment.yml
     ```
   - If the environment already exists, remove it:  
     ```
     conda remove -n <your-repo-name> --all
     ```
   - Activate the environment in two terminal windows:  
     ```
     conda activate <your-repo-name>
     ```

```{note}
If you are familiar with the next generation package manager, [uv](https://docs.astral.sh/uv/), you can instead clone the [EM Quickstart uv](https://github.com/msa-em/em-quickstart-uv) repository and follow the instructions there.
```

### Step 2: Editing Your Article

**Modify Configuration Files**
   - Edit the `myst.yml` file:
     - For local editing, comment out the `jupyter: true` line.
     - Uncomment the lines for local Jupyter server configuration:
       ```yaml
       jupyter:
         server:
           url: 'http://localhost:8888'
           token: '512ac78f14e1141db1fac17e8b4099c1e5bc7d589518b38c'
       ```

**Run Jupyter and MyST**
   - In the first terminal window, start the Jupyter server:  
     ```
     jupyter lab --IdentityProvider.token=512ac78f14e1141db1fac17e8b4099c1e5bc7d589518b38c --ServerApp.allow_origin='http://localhost:3000' --port=8888
     ```
   - In the second terminal window, start the MyST server:  
     ```
     myst start
     ```

**Add Your Article Content**
   - Write your manuscript in MyST Markdown, making sure to organize your sections into separate markdown files, and using subsections where appropriate.
   As you write the article content, embed code, multimedia, and data as needed.
   - Remember that when committing your local `myst.yml` changes, you will need to switch back to `jupyter: true` for the web-based version. 

### Step 3: Previewing and Finalizing

**Preview Your Article**
   - Push your changes to the `dev` branch.
   - Open a draft pull request (PR) into the `main` branch.
   GitHub Actions will deploy a staging site for live previews.
   - Click the "Inspect" link in the GitHub Actions bot message to preview your article on the Curvenote staging site.

**Merge When Ready**
   - Once all content is finalized, merge the PR into the `main` branch.
   Ensure thematic changes are grouped together.

---


## Beginner Users

### Getting Started

If you're new to the tools and processes used for Elemental Microscopy, follow these simpler steps to get started without using GitHub or advanced command-line tools. 
These instructions will guide you through preparing and submitting your manuscript.

### Step 1: Download Template
   - Choose a template to get started, either:
     - The [EM Quickstart Template](https://github.com/msa-em/em-quickstart).
     - The [full EM Template](https://github.com/msa-em/em-template).
   - The templates includes basic formatting, example figures, and placeholders for multimedia or code.
   - Save the template to your computer and open it using any Markdown-compatible editor (e.g., [Sublime](https://www.sublimetext.com/), [Typora](https://typora.io/), [Visual Studio Code](https://code.visualstudio.com/), or a simple text editor).

### Step 2: Edit Your Manuscript
   - Use the downloaded template to write your article, ensuring you:
     - Add clear section headings for organization.
     - Insert links or placeholders for multimedia (e.g., images, videos) and datasets.
     - Include inline code examples or results, if applicable.

### Step 3: Interactive Content
   - If you want to include interactive visualizations or code, let the editorial team know.
   They will guide you on how to use pre-configured Jupyter notebooks or help integrate the interactive elements with you.

### Step 4: Preview Article
   - After editing, send your manuscript and associated files (e.g., images, datasets) to the editorial team, either [Colin](mailto:cophus@stanford.edu) or [George](mailto:gvarnavides@berkeley.edu).
   - The team will provide a preview link for you to review your draft article on the EM platform.

### Step 5: Submit for Review
   - Once you're satisfied with the draft, the editorial team will guide you through the submission process.
   - The article will then go through the open peer review process before publication.


### Notes for Beginner Authors

- **No Installation Required**: Beginner authors do not need to set up a local environment or use GitHub.
All technical configurations will be handled by the editorial team.
- **Focus on Content**: Concentrate on the clarity and organization of your article.
The editorial team will assist with integrating multimedia and code.

---

## Best Practices

- Use templates and examples provided in the repository to guide your writing.
- Ensure all code blocks are reproducible and include inline comments.
- Cite datasets and code repositories using DOIs where possible.

For further assistance, please contact the editorial team at [elementalmicroscopy.com](/editors).
