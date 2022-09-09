---
title: "How to Run a Single Test Jest?"
date: 2022-09-09T14:16:39-05:00
draft: true
---

![Alt text](hero.jpg "Image by https://unsplash.com/es/fotos/lQGJCMY5qcM")


We have hundreds of tests in this project but we need to watch and run just one test case inside one test.

This is a recurring snippet that I always keep forgetting, there are couple of ways to do this but the most straightforward, in my opinion, is to use the test name pattern param (```-t``` or ```-testNamePattern```)

For example, let’s imagine we have these tests:

{{<alert >}}

**./tests/foo.test.js**

{{</alert >}}

```
describe("Foo", () => {
    it("Test A foo", () => {
        expect(true).toBe(true);
    })

     it("Test B foo", () => {
        expect(49).toBe("The meaning of life");
    })
})
```

{{<alert >}}

**./tests/bar.test.js**

{{</alert >}}

```
describe("Bar", () => {
    it("Test A bar", () => {
        expect("bar").toBe("bar");
    })

     it("Test B bar", () => {
        expect(7).toBe("The number of luck");
    })
})
```

—

If we want to run just the ```bar.test.js file``` and the test case ```Test A bar```only we should run the following command:

```
jest -i tests/bar.test.js -c test/our-jest-config.json -t "Test A bar"

```

[Source](https://stackoverflow.com/a/69101127)
