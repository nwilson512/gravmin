---
title: modular-doc
---

### other documentation platforms

* ASCIIdoc
* Framemaker

### Modular Content Management

In the structure outlined in the [about section](/documentation-new/about/), you'll see that the content is all contained in a single folder. This allows us to build documents using a single source of modular topics. Now we can reuse shared topics. Neat, huh?

The topics in modular content management consist of two parts: metadata (in this case: YAML frontmatter) and the markdown content itself. YAML frontmatter contains any kind of useful metadata you can imagine, for example:

  * Publish/Update date
  * Product or category
  * Related topics
  * Topic type
  * Author
  * Anything else

### Setting up modular content infrastructure

Modular content infrastructure isn't easy to set up. This requires quite a lot more forethought and management overhead than writing in a word processor, or even writing into a basic CMS (I'm looking you, WordPress). It requires a powerful content management system and the technical understanding to make that work.

For more detailed information about how modular content infrastructure is set up on this website, sett the [about section](/documentation-new/about/)

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

In the context of steaming vegetables, this exercise is a little bit tedious. After all, if you're not sure how to steam rice, you probably just google the answer, or call your mom. But what happens when we shift to something like a airplane firmware? All of a sudden these related topics matter, and your users probably won't be able to ask their mom. Heck, if your product is suitably niche or proprietary, your users might not even find their answer on google.

Equally important is knowing what not-to-write. To identify things that you shouldn't be writing about, consider the following:

* how many degrees of separation from your product is this detail?
* what will happen if this detail goes unsaid?
* how many people will this detail impact?
* Is this detail someone else's responsibility and can you leverage their documentation?
* what will happen if this detail becomes outdated or wrong?

Some examples of things that you probably wouldn't want to include in example documentation:

* what is the meaning of life?
* who makes rice cookers?
* how long does the cook cycle last on the steam-o-matic steamer?

You can break up this act into a series of DITA-esque topics.
