+++
categories = ["web-dev"]
coders = []
date = 2020-11-22T00:00:00Z
description = "This website!"
github = ["https://github.com/CMarah/personal-website"]
image = "/logos/hugo.svg"
title = "Hugo Website"
type = "portfolio"
[[tech]]
logo = "/logos/hugo.svg"
name = "Hugo"
url = "https://gohugo.io/"
[[tech]]
logo = "/logos/uikit.svg"
name = "UIkit"
url = "https://getuikit.com/"
[[tech]]
logo = "/logos/katex.svg"
name = "KaTeX"
url = "https://katex.org/"
[[tech]]
logo = "/logos/pdfjs.png"
name = "PDF JS"
url = "https://mozilla.github.io/pdf.js/"

+++
This is my personal website, made with Hugo.

## Tech & Choices

### Framework

![Hugo](/logos/hugo.svg "Hugo")

When choosing a framework to build my personal website there were a few factors I took
into consideration, like the kind of content I wanted to host, and its format.
As this is a blog/portfolio/hub, it made sense to have a static site. I don't need any
database or server design, and I would be serving fixed HTML. The significant increase in
speed is always welcome, and I wanted to minimize complexity.

Knowing I wanted a static website, there were a few frameworks I could go for. I chose
_Hugo_ for a few reasons. Firstly, as with every personal project, I was looking to learn
something new. Among the static site generators I hadn't used, Hugo looked interesting and
unique, while still having a significant community. Regarding this last point, the [Hugo
themes list](https://themes.gohugo.io/) seemed like a great starting point, as themes work
out of the box while still being completely customizable. There, I found my starting
theme: Sam Robbin's [Developer's
Portfolio](https://github.com/samrobbins85/hugo-developer-portfolio).

Though at first I found Hugo's structure a bit daunting, once I learned how everything
worked it felt comfortable. Adding new posts is very fast, and Hugo's layout system
feels very natural for this kind of site. As to performance, being a static website it is
obviously extremely fast, just what I wanted.


### Math typesetting library

![KaTeX](/logos/katex.svg "KaTeX")

As I intended to add mathematical content, I needed some way to correctly render LaTeX.
There are two main engines designed to do this: _MathJax_ and _KaTeX_. MathJax is the
classic options, while KaTeX is the newer library, and the one I ended up using. KaTeX is
noticeably faster and seems to be the main choice nowadays. In any case, switching between
both of them isn't difficult, and it can even be done programmatically.

Sadly, Hugo isn't explicitly designed to work with this libraries out of the box,
at least in the current _0.78_ version. To make it work, you need to use the _mmark_
markdown renderer in the posts where you want to use LaTeX. This renderer is deprecated,
so I may have to rework how I do this at some point. This is a big Hugo weakness, and if I
had know earlier I may have chosen another framework. Still, this is not a fundamental
feature, so my current setup is good enough.


### UIkit

![UIkit](/logos/uikit.svg "UIkit")

UIkit was used on my original Hugo theme, so it was natural to keep it. This front-end
framework simplified quite a bit of my CSS workload, and allowed me to keep a consistent
look throughout the site. Lightweight and easy to use, it provided a nice starting point.
