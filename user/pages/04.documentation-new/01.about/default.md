---
title: About
icon: help
hook: "Learn how this site is built, what technologies it is built on, and how you can build one just like it."
---

# How this site is built

This site is built on a the following technologies:

* Google Cloud Platform
* Grav
* GitHub

I've added some plugins to make the site easier to use and look better, specifically:

* [Diagrams](https://github.com/OleVik/grav-plugin-nomnoml-uml-diagrams)
* [Admin panel](https://github.com/getgrav/grav-plugin-admin/blob/develop/README.md)
* [Content injector](https://github.com/getgrav/grav-plugin-page-inject)

I'm using a modified quark grav [theme](https://getgrav.org/downloads/themes).

## Repo flow and configuration overview

full site on local -> full site in repo -> full site on GCP

## Set up your dev server

You can set up and run your own local implementation of this webserver:

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

1. Nav to the location in which you cloned your repo (mine's in the default GitHub directory under Documents): `cd /Users/<username>/Documents/GitHub/gravmin`
2. Run your server `php -S localhost:8000 system/router.php`


## Modify the CSS

! This implementation isn't great, consider building with the command line using something like `npm run watch`

Use the main `theme.scss` file to build the CSS files. I'm using the [sass-autocompile](https://atom.io/packages/sass-autocompile) plugin.

To set up the sass-autocompile plugin, do the following:

  1. install it
  2. add the following string to `filename pattern for 'compressed' compiled files`:
  `../css-compiled/theme.min.css`
  3. add the following path to the `Include paths`:
  `user/themes/quark/scss`

To build the CSS, do the following:

  1. open `themes.scss`
  3. save it

To add a new css file for new template work, do the following:

  1. create a new template partial under:
  `user/themes/quark/scss/`
  > Note: A partial is a file with a leading underscore in the file name: `_filename.scss`

!!! The sass-autocompile will build the `theme.min.css` minified css file with the import sass files and place it in the correct `css-compiled` directory.

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

```
[nom]
[You] -> [My site]
[/nom]
```

## Site Structure

With anything, it helps to have a plan. With a documentation website, doubly so. So here's mine:

[nom]
[Home Page]
[Documentation |
  [example1] -> [modular topics folder]
  [example2] -> [modular topics folder]
  [example3] -> [modular topics folder]
  [modular topics folder |
    [concept topics]
    [task topics]
    [reference topics]
  ]
]
[Network]
[/nom]

The bulk of the complexity with the site lies in the Documentation section, since that's what I do.



Other parts of the site:
* my written articles
* my resume/cv
* my external writing samples


# Design

All good things need some totally dope design elements. That's why I've designed this site's look and feel thusly:

Primary color code:

3900F8

Secondary redish

DD00F8

Tertiary greenish

39E9F8


# The content injection plugin

You can inject content from elsewhere in the site using the following:

The `page-inject` option inserts a page rendered with its template:

`[plugin:page-inject](/route/to/page)`

The `content-inject` option just inserts the plain content:

`[plugin:content-inject](/url/path/to/file)`

This requires that your pages have legitimate routes on the site. So they'll need to be pages in a folder. The folder doesn't need to be routable, and the pages don't need to be published, but they do need to follow the correct format of: `folder/page-folder/default.md`


content injection samples:

[plugin:content-inject](/modular-topics/concept-topic)

[plugin:content-inject](/modular-topics/task-topic)

[plugin:content-inject](/modular-topics/reference-topic)

# Google Cloud Platform Details

Google Cloud Platform (GCP) is large cloud services platform that competes with the likes of Amazon Web Services and Microsoft Azure. Cloud platforms are very large and complex topics, so I'll limit the discussion to the architecture of this site as it relates to GCP.

At the time of writing, traffic and performance requirements are very small and limited a to development scope.

This webserver runs on a single `g1-small` Compute Engine instance. The instance is running a standard [LAMP stack deployment](https://console.cloud.google.com/marketplace/details/click-to-deploy-images/lamp).

The instance has access to 10GB of magnetic drive space.

[plugin:content-inject](/modular-topics/task-create-repository)
