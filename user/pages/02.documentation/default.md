---
title: Documentation
published: false
---

This page will eventually be modular and serve as a jumping off point for the following categories:
* Modular documentation (hook: Find out what modular documentation is, see how I write documentation, view examples)
* About this site (hook: learn how this site is built, what technologies it is built on, and how you can build one just like it)
* My API (hook: Play with my API, learn what it does and how it works)

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

1. Nav to the location in which you cloned your repo (mine's in the default GitHub directory under Documents): `cd /Users/<username>/Documents/GitHub/gravmin`
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




### other documentation platforms

* ASCIIdoc
* Framemaker

### Modular Content Management

In the structure above, you'll see that the content is all contained in a single folder. This allows us to build documents using a single source of modular topics. Now we can reuse shared topics. Neat, huh?

The topics in modular content management consist of two parts: metadata (in this case: YAML frontmatter) and the markdown content itself. YAML frontmatter contains any kind of useful metadata you can imagine, for example:

  * Publish/Update date
  * Product or category
  * Related topics
  * Topic type
  * Author
  * Anything else

### Setting up modular content infrastructure

Modular content infrastructure isn't easy to set up. This requires quite a lot more forethought and management overhead than writing in a word processor, or even writing into a basic CMS (I'm looking you, WordPress). It requires a powerful content management system and the technical understanding to make that work.

Want to learn more {page content field here}? [Hire Me!](google.com). Except don't, since I have a job already, and they like me, and I like them. It's really quite a nice arrangement.

### Markup Details

Modular content markup can be identified by the following principles:

  * Topic-based authorship
  * Inclusion of text variables
  * Centralized content sourcing

#### Topic-based authorship

If you're doing all of the legwork to implement a modular content system, you need to be writing with it in mind. In essence, that's what topic-based authoring is. The modular segments you write must be independently understandable.

Let's look at an example: steaming rice with vegetables

Consider all of the steps that go into steaming rice with vegetables, on the surface it's pretty simple:

1. Gather ingredients
2. Measure the rice, vegetables, water
3. Add everything to the rice steamer
4. Cook it

Let's look again though, this simple task leaves a lot of questions unanswered:

* How much of each ingredient do you add?
* How do you cook it? In a pot, or a steamer? And for how long?
* What kind of rice are you using, and do you need to adjust the water added for different kinds of rice?
* How do you measure the ingredients?

There are even a number of indirect questions we can ask that are related to this task that range from very fundamental to very specific:

* What is/are rice, vegetables, a pot, a measuring cup, or a steamer?
* Where do you buy any of these things?
* What form do vegetables come in? Fresh, frozen, canned, dehydrated.
* What kind of steamer is best for me?

In the context of steaming vegetables, this exercise is a little bit tedious. After all, if you're not sure how to steam rice, you probably just google the answer, or call your mom. But what happens when we shift to something like a webserver? All of a sudden these related topics matter, and your users probably won't be able to ask their mom. Heck, if your product is suitably niche or proprietary, your users might not even find their answer on google.

Equally important is knowing what not-to-write. To identify things that you shouldn't be writing about, consider the following:

* how many degrees of separation from your product is this detail?
* what will happen if this detail goes unsaid?
* how many people will this detail impact?
* Is this detail someone else's responsibility and can you leverage their documentation?

Some examples of things that probably we probably wouldn't want to include in example documentation:

* what is the meaning of life?
* who makes rice cookers?
* how long does the cook cycle last on the steam-o-matic steamer?

You can break up this act into a series of DITA-esque topics.

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
