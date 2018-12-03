---
title: 'Create and Configure your GitHub Repository'
published: false
---

# Create and Configure your GitHub Repository

Create a GitHub repository and prepare it for Grav installation.

## Prerequisites

* The Git command line or desktop application
* A GitHub account

## Go for it

1. [Create a GitHub repository](https://help.github.com/articles/create-a-repo/).
2. [Clone your repository](https://help.github.com/articles/cloning-a-repository/).
3. Create a `.gitignore` file with the following contents and add it to your repository:

```
# Grav Specific
.sass-cache
composer.lock
cache/*
assets/*
logs/*
images/*
user/data/*

# OS Generated
.DS_Store*
ehthumbs.db
Icon?
Thumbs.db
*.swp
```

4. Commit your changes and push them to github.

!!!! You should now have a repository on both your computer and GitHub.com with your `.gitignore` file.

> This documentation contains steps sourced from the following blogs:
  *	https://getgrav.org/blog/developing-with-github-part-2
	* https://www.booleanworld.com/install-grav-cms-debian-ubuntu/
