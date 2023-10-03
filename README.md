# gn-docs
Documentation site for the growth nirvana platform

# How to write a new documentation page?

### 1. Folder
Create a new folder with the name of the section/feature you want to document. (i.e. datasets)

### 2. index.md
Create an index.md file within the folder. This file will be accessible via `/{folder_name}` (i.e. /datasets)

### 3. Other files
Create any markdown file within the folder to document specific features. (i.e. datasets/configuration.md)
The markdown files must have the `parent` frontmatter key set. For instance:
```markdown
---
layout: default
title: Configure a client dataset
parent: Datasets
---
```

Images can also be placed within the folder.

### 4. Just the docs
Just the docs provides utilities, UI components, structuring and many more things. Check them out here https://just-the-docs.com/
