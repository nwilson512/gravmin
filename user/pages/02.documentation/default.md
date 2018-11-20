---
title: Documentation
---

# How this site is built

This site is built on a the following platforms:

* Google Cloud Platform
* Grav
* GitHub

I've added some plugins to make the site easier to use and look better, specifically:

* [diagrams](https://github.com/OleVik/grav-plugin-nomnoml-uml-diagrams)
* [Admin Panel](https://github.com/getgrav/grav-plugin-admin/blob/develop/README.md)

I'm using a modified grav [theme](https://getgrav.org/downloads/themes)

## HowTo

## Repo flow and configuration overview

full site on local -> full site in repo -> full site on GCP

## Set up your dev server

### Perform initial configuration

1. Clone the repo
2. Create a route in your host file:
  1. Go to the hosts file: `cd /etc/hosts`
  2. Enter `127.0.0.1 localhost`
  3. Save it
3. download the latest [grav core](https://getgrav.org/downloads)
4. extract the grav core and copy its contents
5. In the area in which you cloned your repository, paste the grav core contents

### Start your dev server

1. Nav to the location in which you cloned your repo (mine's in the default GitHub directory under Documents): `cd /Users/<username>/Documents/GitHub`
2. Run your server `php -S localhost:8000 system/router.php`

## Fonts

I've also added some super dope google web fonts:

* Asap
* Audiowide
* Hind
* Monoton
* Noto+Sans+JP
* Rosario

Add them in the CSS:

```
font-family: 'Rosario', sans-serif;
font-family: 'Hind', sans-serif;
font-family: 'Asap', sans-serif;
font-family: 'Noto Sans JP', sans-serif;
font-family: 'Monoton', cursive;
font-family: 'Audiowide', cursive;
```

### Using diagrams

For diagrams, use the `nom` shortcode:

[nom]
[You] -> [My site]
[/nom]

## Site Structure

With anything, it helps to have a plan. With a documentation website, doubly so. So here's mine:

[nom]
[Home Page]
[Documentation |
  [example1] -> [content folder]
  [example2] -> [content folder]
  [example3] -> [content folder]
  [content folder |
    [concept topics]
    [task topics]
    [reference topics]
  ]
]
[Network]
[/nom]

The bulk of the complexity with the site lies in the Documentation section, since that's what I do.

Other parts of the site:
my written articles
my resume/cv

### Modular Content Management

In the structure above, you'll see that the content is all contained in a single folder. This allows us to build documents using a single source of modular topics. Now we can reuse shared topics. Neat, huh?

### Setting up modular content infrastructure

Modular content infrastructure isn't easy to set up. This requires quite a lot more forethought and management overhead than writing in a word processor, or even writing into a basic CMS. It requires a powerful content management system and the technical understanding to make that work.

Want to learn more {page content field here}? [Hire Me!](google.com)

# Design

All good things need some totally dope design elements. That's why I've designed this site's look and feel thusly:

Primary color code:

3900F8

Secondary redish

DD00F8

Tertiary greenish

39E9F8
