---
layout: post
title: User Interface
description: "Common web application user interface tips."
tags: [user interface, ui, web, issues]
comments: false
image:
  background: small_steps.png
  feature: shirts.jpg
---

User Experience is one of the most important parts of web applications.

The following are tips and questions to consider when working on your web application user interface.

# Test for Consistency Between Browsers

Are there tests for consistency with:

- [ ] The [Gecko](http://en.wikipedia.org/wiki/Gecko_%28layout_engine%29) engine - i.e. [Firefox](http://firefox.com/).
- [ ] The Webkit engine - i.e. [Safari](http://www.apple.com/safari/).
- [ ] [Chrome](http://www.google.com/chrome).
- [ ] [Opera](http://www.opera.com/).
- [ ] IE Browsers - take advantage of the [Application Compatibility VPC Images](http://www.microsoft.com/Downloads/details.aspx?FamilyID=21eabb90-958f-4b64-b5f1-73d0a413c8ef&displaylang=en).

For IE Browsers, there is a Github project call [ievms](https://github.com/xdissent/ievms) which provides Virtual Machines with IE6, IE7, IE8, IE8, IE10, and IE11.

Also consider how the same browser will render your site on differnet operating systems. Consider a service like [Browsershots](http://www.browsershots.org/) or [Litmus](https://litmus.com/).

# Do your Positive, Negative, and Neutral Buttons look different?

[![Buttons]({{ site.url }}/images/positive-actions-contrast.png)](http://uxmovement.com/buttons/how-button-color-contrast-guides-users-to-action/)
Image from [UX Movement](http://uxmovement.com/buttons/how-button-color-contrast-guides-users-to-action/).

Have your Positive Action buttons and your Neutral and Negative Action buttons look distinctly different.  Notice that in the above example, not only are the colors different, but one is bordered and ther other is filled in, making it [accessible]({{ site.url }}/accessibility) to those with color-blindness.


# Test for Mobile Consistency

Are there tests for consistency with:

- [ ] Android phones and tablets
- [ ] iOS phones and tablets
- [ ] Screen readers
- [ ] Search engines

For more information, check out [Mobile]({{ site.url }}/mobile/) and [Developer Tools]({{ site.url }}/developer-tools/).

# Do you have a staging environment?

Can you deploy updates without affecting your users?

Testing and staging environments are important for being able to test features, architecture, etc without breaking the user's session.

Have an automated way of deploying approved changes to the live site. Consider using a version control system with an automated build system (something like [Maven](http://maven.apache.org/)).

# Are errors handled in a friendly matter?

Users should receive easy to read error messages.

Users should never see:

- Out Of Memory errors
- Raw 404 pages
- Stack Traces

# Is user info crawlable on public pages?

Try not to have users' email in plain text on public facing pages.  They might get spammed.

# Is the `rel="nofollow"` attribute on user-generated links?

Avoid spam by putting the [nofollow](http://en.wikipedia.org/wiki/Nofollow) on user generated links.

# Does your site have built in rate limiting and velocity checking?

Any user actions should have rate limiting and velocity checking built in.  This is also a security issue.

Look into [Coding Horror's post on rate limiting and velocity checking](http://blog.codinghorror.com/rate-limiting-and-velocity-checking/) for more information.

# No inline styles

All CSS should be in stylesheets.

# Accessibility

Check to make sure your website is navigable from screen readers.

If you are using [Twitter Bootstrap](http://getbootstrap.com/), look into the [Bootstrap accessibility plugin](http://paypal.github.io/bootstrap-accessibility-plugin/).

If you are using [Foundation](http://foundation.zurb.com/), look into how [Foundation is built around accessibility](http://zurb.com/article/1337/foundation-now-helps-you-build-accessible).

For more on accessibility, see [the full page on Accessibility]({{ site.url }}/accessibility).

# Are you using HTML5?

If you can, start out by using HTML5.  If you do so, remember to include the [HTML5 Shiv](http://en.wikipedia.org/wiki/HTML5_Shiv) (or Shim) so that IE version before 9 can use HTML5 elements.

Look into [HTML5 Boilerplate](http://html5boilerplate.com/) or [Initialzr](http://www.initializr.com/) for an HTML5 boilerplate that comes with the HTML5 shim, normalize.css, and Modernizr.

# Consider Using Normalize.css

Consider reseting the browser style sheets or using [normalize.css](http://necolas.github.io/normalize.css/) for consistency between browsers.

# Are you using Semantic HTML?

Recent HTML standards discourage the use of the `<i>` in preference for the `<em>` tag. Other HTML5 tas to consider using are:

- `<article>`
- `<aside>`
- `<details>`
- `<figcaption>`
- `<figure>`
- `<footer>`
- `<header>`
- `<main>`
- `<mark>`
- `<nav>`
- `<section>`
- `<summary>`
- `<time>`

# Redirect after a POST

After a user POSTs data, redirect to a success page, to prevent a refresh from submitting data again.

# Use Progressive Enhancement

Allow graceful degradation of your website.

- [ ] Basic content should be accessible to all web browsers
- [ ] Basic functionality should be accessible to all web browsers
- [ ] Sparse, semantic markup contains all content
- [ ] Enhanced layout is provided by externally linked CSS
- [ ] Enhanced behavior is provided by unobtrusive, externally linked JavaScript
- [ ] End-user web browser preferences are respected

See [Progressive Enhancement](http://en.wikipedia.org/wiki/Progressive_enhancement) for more information.

# Validate Forms

Going along with [Security]({{ site.url }}/security/), make sure to validate all form input on the server side and give useful errors back to the user.  Once proper form security handling has been implemented, add in client side validation.  You can use HTML5's simple validation to add a small layer of responsive validation:

```html
<input id="username" placeholder="John Jones" required>
```

You can use the `required` attribute to let users know on the client side before they submit their form that a field is required.

You can use the new input type to help with input validation as well:

```html
<input type="email" required>
```

You can mark invalid input with CSS as well:

```css
input:required:invalid {
  background: red;
}
```

Checkout [Form Validation in HTML 5](http://basicuse.net/articles/pl/textile/html_css/form_validation_in_html5) for more information.

# Use CSS Animations over JavaScript Animations

You can now use CSS animations instead of relying on JavaScript.  You can read more about CSS animations on the [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Using_CSS_animations).

