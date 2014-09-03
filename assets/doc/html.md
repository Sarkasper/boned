[Documentation
table of contents](TOC.md)

# The HTML

## The `no-js` class

Allows you to more easily explicitly add custom styles when JavaScript is
disabled (`no-js`) or enabled (`js`). More here: [Avoiding the
FOUC](http://paulirish.com/2009/avoiding-the-fouc-v3/).

## Language attribute

Please consider specifying the language of your content by adding the `lang`
attribute to `<html>` as in this example:

```html
<html class="no-js" lang="en">
```

## The order of meta tags, and `<title>`

As recommended by [the HTML5
spec](http://www.whatwg.org/specs/web-apps/current-work/complete/semantics.html#charset)
(4.2.5.5 Specifying the document's character encoding), add your charset
declaration early (before any ASCII art ;) to avoid a potential
[encoding-related security
issue](http://code.google.com/p/doctype-mirror/wiki/ArticleUtf7) in IE. It
should come in the first [1024
bytes](http://www.whatwg.org/specs/web-apps/current-work/multipage/semantics.html#charset).

The charset should also come before the `<title>` tag, due to [potential XSS
vectors](http://code.google.com/p/doctype-mirror/wiki/ArticleUtf7).

The meta tag for compatibility mode [needs to be before all elements except
title and meta](http://h5bp.com/f "Defining Document Compatibility - MSDN").


## Mobile viewport

There are a few different options that you can use with the [`viewport` meta
tag](https://docs.google.com/present/view?id=dkx3qtm_22dxsrgcf4 "Viewport and
Media Queries - The Complete Idiot's Guide"). You can find out more in [the
Apple developer docs](http://j.mp/mobileviewport). HTML5 Boilerplate comes with
a simple setup that strikes a good balance for general use cases.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

## Modernizr

[Modernizr](http://modernizr.com) is a JavaScript library which adds classes to
the `html` element based on the results of feature test and which ensures that
all browsers can make use of HTML5 elements (as it includes the HTML5 Shiv).
This allows you to target parts of your CSS and JavaScript based on the
features supported by a browser.

In general, in order to keep page load times to a minimum, it's best to call
any JavaScript at the end of the page because if a script is slow to load
from an external server it may cause the whole page to hang. That said, the
Modernizr script *needs* to run *before* the browser begins rendering the page,
so that browsers lacking support for some of the new HTML5 elements are able to
handle them properly. Therefore the Modernizr script is the only JavaScript
file synchronously loaded at the top of the document.


## The content area

The central part of the boilerplate template is pretty much empty. This is
intentional.

### BrowseHappy Prompt

The main content area of the boilerplate includes a prompt to install an up to
date browser for users of IE 6-9. If you intended to support IE 6-9, then you
should remove the snippet of code.
