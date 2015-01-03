---
layout: post
title: RESTful Interfaces
description: "restful interface tips."
tags: [rest, web, issues]
comments: false
image:
  background: small_steps.png
  feature: mac.jpg
---

RESTful APIs are a common way for applications to be able to communicate with each other.  An important part about RESTful APIs is that they are *consistent*.  Naming, verbage, actions, and errors should be consistent within your API and with how other APIs behave.

Here are some tips and questions that you should ask yourself when developing an API.

# Are you using PUT and POST correctly?

Both PUT and POST can be used for creating. You do not need to support both PUT and POST. Consider the following design decisions:

- Do you name your URL objects you create explicitly, or let the server decide? If you name them then use PUT. If you let the server decide then use POST.
- PUT is idempotent, so if you PUT an object twice, it has no effect. This is a nice property, so I would use PUT when possible.
- You can update or create a resource with PUT with the same object URL
- With POST you can have 2 requests coming in at the same time making modifications to a URL, and they may update different parts of the object.

See [this StackOverflow question for more information](http://stackoverflow.com/questions/630453/put-vs-post-in-rest).

# Are you using appropriate verbs?

When making a REST API, your verbs are your request types, not actual verbs in your URL!  Your URLs should use nouns, not verbs!  Remember to use the plural form for multiple results.

Use your URLs to specify your objects.  Here are some examples of RESTful style requests:

**Obtain 1 Question**
```
GET /questions/<question>
```

**Obtain All Questions**
```
GET /questions
```

**Append/Update Question**
```
POST /questions/<existing_question>
```

**Create a New Question**
```
PUT /questions/<new_question>
```

**Overwrite a Question**
```
PUT /questions/<existing_question>
```

**Delete Question**
```
DELETE /questions/<existing_question>
```

# Nested Resources should be exenstions, not entirely different queries

If you want to get answers to a question, using the above examples as a starting point, the URL should be:

```
GET /questions/1/answers
```

This is nested routing and it helps for a cleaner design.

# Do you have a plan to version your API?

There are different ways to version your API, but it's nice to plan ahead in order for consumers of your API to be prepared.

[Github uses](https://developer.github.com/v3/media/#request-specific-version) the `Accept` HTTP header to pass the desired version to the API.

Another less common method is to version the application in the URL: `/api/v1/...`.

