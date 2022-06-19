---
title: "Draft.js"
date: 2022-06-19T23:31:29+02:00
author: "Carlos"
description: "Draft.js review & using custom decorators"
type: "post"
---


An extensible, powerful text editor can be of great use in many sites. [Draft.js](https://draftjs.org/)
is a rich text editor framework for React, with some very deep customizability. Sadly, this seems
to come at the cost of an API which feels cumbersome at times, and the docs are lacking.
In any case, the framework is still being slowly developed and is one of the main options to consider.


I used Draft.js to add some new functionalities to basic `textarea`s. In particular, I needed
to be able to add some variables, which where rendered with a particular component. This is one
of the big reasons for choosing the framework, as one can render specific sections of text
(called entities) in specific ways.


### Entities & Custom components

The entities API is draft's way of adding metadata to text ranges. This may be used to save
a link's href in the corresponding entity, or an image's info. Entities also have a concept called mutability.
`Immutable` entities are treated as a single item, not a collection of characters, which means they can't be
altered without completely removing the entity. Entities are some of the building blocks of Draft.js.

As explained in [their docs](https://draftjs.org/docs/advanced-topics-block-components), Draft.js
also allows passing a `blockRendererFn` prop to the editor, which will display entities or blocks of text using specific
components. This is very powerful, as one can therefore render different text sections in different ways.
In particular, I had a complex component which displayed a popup on click. This popup hosts a menu which allows
modifying the entities' data.
Coding this seemed to be a bit beyond what Draft.js is intended for, as I found quite a few difficulties.
Specifically, the custom component must have a `span` as its root, which may prove too limiting in some cases.


### APIs & Docs

My main gripe with Draft.js was probably how cumbersome the APIs where. I understand a meticulous API is necessary to have
a deeply customizable framework, but I still find doing some operations to be quite tiring and inconsistent. In particular,
managing the selected text and where the cursor is becomes a bit tedious. Fixing bugs I found was a process
of trial and error, as the doc made no mention of some behaviours and the community is quite small.
As mentioned, the doc is far from perfect, as it seems to be missing some slightly relevant sections, such as the valid
values for certain parameters.

I haven't touched on it, but Draft also comes with a variety of rich text editor features, as seen in the screenshot.
If this is the extent of what you're looking to use the editor for, Draft.js is probably a safe bet.

![Draft.js screenshot](/images/blog/draft1.png)

To be fair, I think I may have been asking too much of the framework, and my use case was particularly advanced.
I may consider using Draft.js in the future, but as it stands I'm not sure I'd recommend it. The editor also has a few
bugs, such as the cursor moving incorrectly when placing certain Spanish characters (and this is on a clean install,
without me adding any code). As an alternative, I'll try [Slate.js](https://www.slatejs.org/examples/richtext) next time.
