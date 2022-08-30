---
title: "How to print the entire component using screen.debug() in React Testing Library?"
description: "I love React Testing Library and if you’re here you love it too, but when we’re testing a component with many lines of JSX and trying to print it React Testing Library will not show the entire component."
tags: ["frontend", "software development", "react", "unit testing", "react testing library", "how to"]
date: 2022-08-30T16:51:47-05:00
draft: false
---

I love React Testing Library and if you’re here you love it too, but when we’re testing a component with many lines of JSX and trying to print it React Testing Library will not show the entire component.

**Problem**

```
// Problem 🔴
screen.debug() 

```

**Solution**

Luckily the solution to this problem is straightforward, the following command will print the whole component in the console.

```
// Solution ✅
screen.debug(undefined, Infinity) 

```

[Source](https://github.com/testing-library/react-testing-library/issues/503#issuecomment-853783968)

