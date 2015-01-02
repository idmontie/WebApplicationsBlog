---
layout: post
title: RESTful Interfaces
description: "restful interface tips."
tags: [rest, web, issues]
image:
  background: small_steps.png
---

# Are you using PUT and POST correctly?

Both PUT and POST can be used for creating. You do not need to support both PUT and POST. Consider the following design decisions:

- Do you name your URL objects you create explicitly, or let the server decide? If you name them then use PUT. If you let the server decide then use POST.
- PUT is idempotent, so if you PUT an object twice, it has no effect. This is a nice property, so I would use PUT when possible.
- You can update or create a resource with PUT with the same object URL
- With POST you can have 2 requests coming in at the same time making modifications to a URL, and they may update different parts of the object.

See [this StackOverflow question for more information](http://stackoverflow.com/questions/630453/put-vs-post-in-rest).

# Are you using appropriate verbs?

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