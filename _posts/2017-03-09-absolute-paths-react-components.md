---
title: "Absolute Paths for React Components"
date: 2017-03-09
category: developer
excerpt: "Because I got real tired at maintaining relative imports across my app"
---

Today, I was working on a new React project at work and got really annoyed at writing `import Component from '../../some/other/directory';`. I got even more annoyed when my guessed path was wrong. And then I had to move some components around and do it all over again.

That's when I decided to fix it.

I did some searching to see what options I had. There were plenty, but a lot seemed like poor solutions or relied on Webpack configuration. Since we used `create-react-app` to bootstrap this project, the latter wasn't an option. We've been prepared to `eject` when necessary, but I was reticent to pull the trigger just for this.

Luckily, I found this [pull request][cra-pr] opened six days ago. Apparently, cra's tooling already supports absolute imports out of the box, they just don't advertise it. This PR just adds some documentation.

1. create a `.env` file in the project root
2. in it, add `NODE_PATH=src`
3. remove the `.env` file from the `.gitignore`

Start serving your app and test it out on `src/index.js`. You can change `import App from './App';` to `import App from 'App';` and it should still work!

It might not seem like a huge change with this example, but the implications are huge. Say you have a deeply nested component at `/src/path/to/my/Component.js`. Now you can import it in any other file of your app with `import Component from 'path/to/my/Component';`. Hurray! No more `..`s or guessed file paths. And if you ever have to move that component, you can do a global find and replace for the new import path.

Breathe easy knowing your app is a little more future-proofed.

---

**Sources:**

- [create-react-app PR #1712][cra-pr]

[cra-pr]: https://github.com/facebookincubator/create-react-app/pull/1712

