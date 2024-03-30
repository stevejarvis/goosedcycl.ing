---
title: "Authoring Stuff on this Blog"
excerpt: "A kinda meta post, about contributing to this site."
last_modified_at: 2024-03-29
comments: false
---

This site is hosted on GitHub Pages, built with Jekyll, and all the source is on 
[GitHub here](https://github.com/stevejarvis/goosedcycl.ing). Every new addition to `main` is built and shipped 
fresh to the live page at [goosedcycl.ing](https://www.goosedcycl.ing). 

There's just a few steps to contribute here.

# GitHub
Do you know how to use GitHub? If not, let's just chat. 
[Here's the gist from GitHub](https://docs.github.com/en/get-started/using-github/github-flow) but if you're actually contributing to this we know each other, let's figure it out. There's options to make it easier.

# Make Yourself a Short Bio
This is a step you only gotta do once. Look in `_data/authors.yml`, and add a bio for yourself there,
including a bio pic in `assets/`. You can include as much as you want really, all the following is supported:

```yaml
# /_data/authors.yml

Billy Rick:
  name        : "Billy Rick"
  bio         : "What do you want, jewels? I am a very extravagant man."
  avatar      : "/assets/images/bio-photo-2.jpg"
  links:
    - label: "Email"
      icon: "fas fa-fw fa-envelope-square"
      url: "mailto:billyrick@rick.com"
    - label: "Website"
      icon: "fas fa-fw fa-link"
      url: "https://thewhip.com"
    - label: "Twitter"
      icon: "fab fa-fw fa-twitter-square"
      url: "https://twitter.com/extravagantman"
```

# Create a Post
Make a new file in `_posts/`. Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.md`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers.
After that, include the necessary front matter. Basically copy an existing one and change to suit.
One piece of this front matter is actually your author profile:

```yaml
author: Billy Rick
```

These files support Markdown. It's pretty standard a lot of places, so you may be familiar, but 
[here's all the nitty gritty details](https://github.github.com/gfm/). You can also use [emojis](https://gist.github.com/rxaviers/7360908).

It's also pretty easy to add photos. Use your tool of choice to scale down high-res photos (for performance reasons). 
Exactly "how big is right" depends on the situation, but consider a 27" 4k monitor is 3840 pixels wide, so more than 
that is excessive for a browser display, and everyone is probably on their phone, so much less is usually preferable.
I'd shoot for 1024 on the long edge.

The code below looks more complicated than it is. First `capture` is the image path, second is the caption, and
the `<figure>` block displays it (copy/paste it and just change the references to `fig_img` and `fig_caption`, whatever
you named the two `capture` blocks).

{% raw %}
```liquid
{% capture fig_img %}
[![Foo](/assets/images/goosed.png)](/assets/images/goosed.png)
{% endcapture %}

{% capture fig_caption %}
Self-portrait. Crayon on paper. 2024.
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>{{ fig_caption | markdownify | remove: "<p>" | remove: "</p>" }}</figcaption>
</figure>
```
{% endraw %}

The :point_up: will render the image as below :point_down:

{% capture fig_img %}
[![Foo](/assets/images/goosed.png)](/assets/images/goosed.png)
{% endcapture %}

{% capture fig_caption %}
Self-portrait. Crayon on paper. 2024.
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>{{ fig_caption | markdownify | remove: "<p>" | remove: "</p>" }}</figcaption>
</figure>

You got the idea. If you're wondering how to do something, you can obviously ask away, otherwise the [theme's docs
are really very good](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/). The theme also
has [a bunch of example posts demonstrating different features](https://github.com/mmistakes/minimal-mistakes/tree/master/docs/_posts),
copy tricks from there.