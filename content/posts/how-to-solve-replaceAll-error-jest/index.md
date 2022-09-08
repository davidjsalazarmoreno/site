---
title: "How to Solve the replaceAll error in Jest?"
description: "One time I was working on a legacy React project, I ran a recently added unit test and I got this error: TypeError: replaceAll is not a function."
tags: ["frontend", "software development", "react", "unit testing", "react testing library", "how to", "troubleshooting"]
date: 2022-09-05T16:09:53-05:00
draft: false
---

One time I was working on a legacy React project, I ran a recently added unit test and I got this error:

**Problem**

{{< alert >}}

Jest: TypeError: replaceAll is not a function

{{< /alert >}}

I was confused at the beginning because in the browser the component was working like a charm using [replaceAll](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replaceAll) method, but it turns out that _replaceAll is a new function not implemented in all browsers nor older Node.js versions._

**Solution**

{{< alert "check" >}}

Install the replaceAll polyfill and add it to the jest setup configuration file.

{{< /alert >}}

1. Install the replaceAll

```
npm i string.prototype.replaceall
```

2. Modify your Jest config, add a setupFilesAfterEnv property as below: 

```JSON
{
  "jest": {
    "setupFilesAfterEnv": ["<rootDir>/jestSetup.js"]
  }
}

```

3. Add the following code to your jestSetup file

```js
import replaceAllInserter from 'string.prototype.replaceall';

replaceAllInserter.shim();
```

Happy coding!

[Source](https://stackoverflow.com/questions/65295584/jest-typeerror-replaceall-is-not-a-function/67877325#67877325)

---

**Please, subscribe to our newsletter to get our amazing content!** 
<br />
<iframe src="https://embeds.beehiiv.com/a73a7bea-7c89-48e9-bf8d-65554157c3d4?slim=true" data-test-id="beehiiv-embed" frameborder="0" scrolling="no" style="margin: 0; border-radius: 0px !important; background-color: transparent;" width="100%"></iframe>