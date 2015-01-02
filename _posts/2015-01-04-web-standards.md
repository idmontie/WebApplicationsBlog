---
layout: post
title: Web Standards
description: "Common web application web standards tips."
tags: [standards, web, issues]
comments: false
image:
  background: small_steps.png
  feature: ruler.jpg
---

# Check that GET and POST Requests are Used Properly

`GET` request should be for requesting information.

`POST` requests should be for sending information.

A `GET` request should not change the object that is being requests.

# Validate your HTML and CSS

Write your [XHTML](http://www.w3.org/TR/xhtml1/) or [HTML](http://www.w3.org/TR/REC-html40/) and [CSS](http://www.w3.org/TR/CSS2/) according to [the W3C specifications](http://www.w3.org/TR/) and make sure they [validate](http://validator.w3.org/).

Avoid browser quirks modes by doing this.

# Use 301 and 302 Redirects Correctly

According to [Bigoak Inc](http://www.bigoakinc.com/blog/when-to-use-a-301-vs-302-redirect/):

> All three major search engines handle 301 redirects the same, that is to say they ignore the original URL and instead index the destination URL.

> The three major engines handle 302 redirects very differently, and because of this 302s are typically not recommended.

Best practice is to use 301 redirects (which are permanent and are usually cached by the browser).  For temporary moves, use 302 redirects.

# Force IE to Use Unicode for Parameters

If you have ever seen `utf8=✓` in the parameter listing of a url, it's in order to [force Internet Explorer (5, 6, 7 and 8) to encode its parameters as unicode](http://stackoverflow.com/questions/3222013/what-is-the-snowman-param-in-ruby-on-rails-3-forms-for/3348524#3348524).  