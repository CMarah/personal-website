---
title: "Hosting a Hugo website on GitHub pages"
date: 2021-03-12T21:14:34+06:00
description: "How to set up & organize a web on GitHub pages powered by Hugo"
author: "Carlos"
type: "post"
---

When I set off to create a personal website, I knew I wanted it to be static. A blog
should be fast & lightweight, and the simple logic is always a plus. Nowadays there is no
shortage of static site generators, like Jekyll or Gatsby, and given my experience with
JS & React these were some very natural options. Still, I ended up choosing Hugo,
as I had read some great reviews about it, and wanted to learn something a bit different.

[Hugo](https://gohugo.io/) is an open-source static site generator. Hugo's text is
written in markdown, while its layouts are written in plain HTML + JS, and uses Go to
build the site.
This means uploading new content is very fast, and I only need to worry about coding
and designing if I want to create a new section. In fact, thanks to Hugo's community,
which has created hundreds of [_themes_](https://themes.gohugo.io/), it's
possible to write a Hugo website without any coding experience at all.

Finally, to host the site I chose GitHub pages. As I stated, I wanted a something very simple,
and I don't need to look any further: GH pages is a perfectly fine way of serving a few
files, which is what a Hugo site ends up being.


### Hugo

My starting point was Sam Robbin's great
[theme](https://github.com/samrobbins85/portfolio-website-v2), as it had the clean
and simple feel I was looking for. Though I rewrote quite a bit of the code, it was a
pleasure using it. I'd say starting from a particular theme is extremely comfortable, as I
can just need to focus on adding content, and progressively change the underlying code if
needed. One of the few gripes I had with Hugo was in these early stages, as it is very
strict on where and how to have your code structured, but was still quite manageable, and
entirely optional.

To work with Hugo I use its CLI tool. When testing/writing locally, `hugo server` will
make your site available at _localhost_. Hugo comes with LiveReload built in, and given
its speed, any changes made will display almost intantly. When ready to publish your
changes, running `hugo` will build the `public` folder, containing the site's content.
This is the folder we want to host in GitHub pages, so creating a repo there would be
quite natural. But I wanted to have the whole site on a single repo for simplicity.


### GitHub & GitHub pages

There are multiple ways of achieving this, but here's a very simple one.
GitHub pages allows choosing which branch to use as source;
the idea is to have my main branch contain the source and a different one
contain the built site. To comfortably do this, I just need a few extra steps:
1) Add `public/` to `.gitignore`, so I can keep a clean directory.
2) Create a branch in the `public/` folder, which will contain the built site:
```git worktree add -B gh-pages public upstream/gh-pages```

To upload new content, I just need to run `hugo` to build the site, move to the `public/`
folder and publish to GitHub. I wrote a simple script to do this,
[publish.sh](https://github.com/CMarah/personal-website/blob/main/publish.sh).

![GitHub Pages menu](/images/blog/ghpages.png)
