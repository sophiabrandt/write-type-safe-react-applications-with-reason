title: Write Type-Safe React Applications With Reason
class: animation-fade
layout: true

<!-- This slide will serve as the base layout for all your slides -->
.bottom-bar[
  {{title}}
]

---

class: impact

# {{title}}

---

class: impact

## An introduction to ReasonML

---

# About Me
--

Hi, my name is **Sophia Brandt**. 👋

--


I work as a **tax officer**. 🏢  

I do exciting things like **auditing tax returns**.


--

In my spare time, I learned coding. 💻

--

I started with HTML, CSS, and JavaScript.

--

And then I learned **React.js**.


---

class: middle

## This talk will be about JavaScript, React, and ReasonML from a **beginner's perspective**.

---

# Agenda
--

* The Problem with JavaScript & React.js 👎
--

* Alternatives? 🛣
--

* ReasonML, And Why? 🤔
--

* Show Me Some Code ⌨
--

* Don't Use ReasonML 🚫
--

* Why I **Like** ReasonML ❤️
--

* ReasonML - yay or nay? 📝
--


If you have any questions, raise your hand please! ✋

---

# The Problem with JavaScript & React.js

---

class: middle
.big[Who has used JavaScript or React before? ✋]

---

class:middle, center
```javascript
Uncaught TypeError: Cannot read property 'body' of undefined
```
--
```javascript
Uncaught TypeError: undefined is not a function
```
---

class:impact

.big[JavaScript is **brittle**.]

---

# Alternatives
--

## What Can We Do to Write Robust Front-End Apps?
--
---

class:impact

.big[Can we use a **type-system**?]
---

For example,
--

* TypeScript?
--

* PureScript?

--
* Elm?

---

## TypeScript

* unsound type system
* `<any>` type
* confusing for a beginner
* slow compiler

---

## PureScript

* high barrier of entry
* inspired by Haskell
* Monads!

---

## Elm

* focus on _purity_: lots of boilerplate
* limited interop with JavaScript

---

class: impact

# ReasonML, and Why?

---
* React as first intended
--

* ReasonML is **OCaml** under the hood, but with a familiar syntax
--

* solid type system: 100% coverage
--

* excellent type inference
--

* fast compiler
--

* immutable by default
--

* _practical_: you _can_ do side-effects, and mutations
--

* it nicely maps over React's syntax
--

* work with JavaScript ecosystem: build tools, package management
--



---

class: impact

# Demo

---

# Don't Use ReasonML
--

* **steep learning curve**
  * if you only know dynamically typed languages
  * it's _not_ JavaScript
--

* small community & ecosystem
  * but they are very friendly!
  * you might need to write bindings to libraries yourself
--

* bad documentation
  * Reason docs, BuckleScript docs, ReasonReact docs???
  * it will get better
  * [reasonml.org][reasonmlorg]

---

# Why I like ReasonML

```reasonml
type option('a) = None | Some('a)
```
--

* no more `undefined`
* a wrapper around a value that _maybe_ exists
---

```reasonml
let licenseNumber =
  if (personHasACar) {
    Some(5);
  } else {
    None;
  };
```

Later:
```reasonml

switch (licenseNumber) {
| None => print_endline("The person doesn't have a car")
| Some(number) =>
  print_endline("The license number is " ++ string_of_int(number))
};

```
---

* `variant` types: make impossible states ... impossible

--

```reasonml

type payload =
  | BadResult(int)
  | GoodResult(string)
  | NoResult;
```
--
* **pattern-matching**

```reasonml
let data = GoodResult("Product shipped!");

let message =
  switch (data) {
  | GoodResult(theMessage) => "Success! " ++ theMessage
  | BadResult(errorCode) => "Error! Error code: " ++
    string_of_int(errorCode)
  };
```
---

class: impact

## ReasonML - yay or nay?

ReasonML is an **functional, immutable, type-safe** alternative to vanilla React.js.

ReasonML is **fun**.

You **have to learn a new way of thinking**.

---

class: impact

# ReasonML: yay! 🙌

---

class:impact

(decide for yourself)

---

class: full

---
# Links

- [ReasonML Website][official]
- [ReasonML Documentation Platform][reasonmlorg]
- [ReasonReact][reasonreact]

# My links

- Website: [https://wwww.sophiabrandt.com](https://wwww.sophiabrandt.com)
- Blog: [https://www.rockyourcode.com](https://wwww.rockyourcode.com)
- Twitter: [https://twitter.com/hisophiabrandt](https://twitter.com/hisophiabrandt)


[reasonmlorg]: https://reasonml.org/
[official]:https://reasonml.github.io/
[reasonreact]:https://reasonml.github.io/reason-react/en/
[bucklescript]: https://bucklescript.github.io/en/
