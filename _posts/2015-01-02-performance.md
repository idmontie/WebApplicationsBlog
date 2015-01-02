---
layout: post
title: Performance
description: "Common web application performance tips."
tags: [performance, web, issues]
comments: false
image:
  background: small_steps.png
---

# Cache Pages

Dynamic pages should be cached in order to improve performance.  Understand how [Web Caching](https://www.mnot.net/cache_docs/) works.

# Use Cache Manifest for Offline Performance

If you would like your page to be accessible offline after a user has already visited it, look into the [Cache Manifest](http://www.w3.org/TR/2011/WD-html5-20110525/offline.html).

# Optimize Images

Compress and crop images for best performance.

# Gzip Content

Most web servers can be configured to automatically do this for you.  Look into [Yahoo's Developer Network discussion](https://developer.yahoo.com/performance/rules.html#gzip) for more information.

# Concatenate Stylesheets and Script Files

Before deploying to production, concatenate Stylesheets and Script files to reduce the number of brwoser connections and improve gzip compression.  There are many solutions to concatinating and compressing CSS and JavaScript files.  You can look into [Grunt](http://gruntjs.com/) for a Node.js solution.

# Use CSS Image Sprites When Possible

Use [CSS Image Sprites](http://alistapart.com/article/sprites) when possible for small related images like toolbars.  The helps minimize HTTP requess and improves gzip compression.

# Split Static Content to Its Own Domain

Static content like images, CSS, JavaScript, and other content should go in a separate domain that *does not use cookies*.  Cookies are sent with every request to the domain and all of its subdomains.  Use a Content Delivery Network (CDN) if possible.

# Minify JavasScript

Minify your JavaScript if possible.  Use the [Google Closure Compiler](https://developers.google.com/closure/compiler/) or look into [this Stackoverflow question for concatenating and minifying JavaScript files in Node](http://stackoverflow.com/questions/6539837/concat-and-minify-js-files-in-node).

# Make a Favicon.ico File

Make sure there’s a `favicon.ico` file in the root of the site, i.e. `/favicon.ico`. [Browsers will automatically request it](https://mathiasbynens.be/notes/rel-shortcut-icon), even if the icon isn’t mentioned in the HTML at all. If you don’t have a `/favicon.ico`, this will result in a lot of 404s, draining your server’s bandwidth.

Check your Favicon against [The Real Favicon Generator](http://realfavicongenerator.net/).  It takes care of favicons for:

* Desktop Browsers
* iOS Home Screen (Favorite icons)
* Android Home Screen (Favorite icons)
* Windows 8 Tile (Favorite tiles)
* Windows Task Bar (App style icon)

It also helps you compress the icons and generates the HTML markup for you.