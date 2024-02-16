---
author: Naman Gupta
pubDatetime: 2024-02-15T12:16:02.856Z
title: Getting started with Bun 1.x
slug: getting-started-with-bun
featured: true
ogImage: https://ik.imagekit.io/insanenaman/blog/bun.svg?updatedAt=1707990953822
tags:
  - bun
  - beginner
description: "Getting started with Bun 1.x. A new age runtime solving many issue at once."
---

![Bun Cover Image](https://ik.imagekit.io/insanenaman/blog/Hi,%20I%20am%20Bun..png?updatedAt=1708081293157)

## Table of contents

## What is Bun?

Just Imagine a [Node.js](https://nodejs.org/)-like runtime but with added features, that you can seamlessly swap in for Node.js

### Introduction

[Bun](https://bun.sh/) is dubbed as an "all-inclusive JavaScript runtime & toolkit engineered for speed, equipped with a bundler, test runner, and Node.js-compatible package manager." It asserts its capability to process at least 3 to 5 times more requests per second than Node.js, particularly tested in scenarios such as serving Server-Rendered React pages.

> Benchmarks may be differ from case to case but it is definitely faster in many cases.

### Installation

Bun offers many ways to [install](https://bun.sh/docs/installation). Simple bash command looks like this:

```
curl -fsSL https://bun.sh/install | bash
```

If you are using Homebrew then you can do something like this:

```
$ brew tap oven-sh/bun
$ brew install bun
```

### Comparison with Node.js

In addition to the main features discussed in next section, Bun also streamlines Developer Experience (DX) in several ways, such as:

- No more different version (LTS/Current)

  - Bun simplifies the process by offering a single version at any given time. Users can install it once and easily upgrade it as needed over time.
  - This approach saves developers from having to use additional tools like nvm or volta to manage different versions, streamlining the development process.

- Simple upgrade command

  - Bun offers simple upgrade command to upgrade its version

  ```
  $ bun upgrade
  ```

- Same commands as node.js and [npm](https://www.npmjs.com/)
  - To run an application (runs dev script mentioned in package.json)
  ```
  $ bun dev
  ```
  - To install all dependencies listed under package.json
  ```
  $ bun install
  ```
  - To kickoff a new project (creates package.json)
  ```
  $ bun init
  ```
  - To install a dependency (its similar to yarn)
  ```
  $ bun add `dependency_name`
  ```

## What Bun exactly offers

### Runtime

> An environment or tool that comprehends and executes your JavaScript code while providing additional functionalities such as supporting asynchronous operations and executing multiple tasks simultaneously using workers.

In today's landscape, JavaScript developers are heavily reliant on Node.js as their primary tool, and Bun recognizes this. It offers a seamless drop-in replacement, meaning you can seamlessly substitute Bun for Node.js without disrupting your existing codebase. Built on top of Zig, Bun ensures compatibility while enhancing performance and functionality.

### Package Manager

> A dependency management tool for your codebase, similar to npm or Yarn.

Similar to Node.js with npm, Bun includes its own built-in package manager. Notably, Bun's package manager boasts exceptional speed by employing a global cache and efficient package reuse. One can get performance like [`pnpm`](https://pnpm.io/) without installing another package manager.

### Bundler

> A tool essential for frontend development, capable of bundling your code, splitting it into chunks, and eliminating dead code through tree shaking. Common ones are webpack, Vite, parcel etc.

Bun aims to be a replacement of bundler tools as well in the future. Bundler is one of the most important tool in frontend dev chain but its not at a stage to compete with more mature options like [`Vite`](https://vitejs.dev/) because it has better plugins and works well with other tools.

### Native TS Support

> Bun natively supports TypeScript, eliminating the need for additional tools like ts-node.

While the community has developed tools like [`ts-node`](https://www.npmjs.com/package/ts-node) to enhance [TypeScript](https://www.typescriptlang.org/) support, Bun offers native support right out of the box. This means you can spend less time configuring your project for [TypeScript](https://www.typescriptlang.org/) and get started more quickly.

### Test Runner

> A tool which run your tests like Vitest, jest etc

Both Node.js and Bun now come equipped with native test runners, providing seamless tooling to execute your tests. Unlike Jest, where additional integration is required for [TypeScript](https://www.typescriptlang.org/) tests due to Node.js not transpiling TS by default, Bun's built-in TypeScript support simplifies running tests without the need for extra configuration. `[Jest](https://jestjs.io/)/[Vitest](https://vitest.dev/) also takes more time to run the same tests. So, choose native wherever you can.`

### And much more

> WebSocket API, DB drivers etc

Bun offers APIs like `WebSocket` ([Perf numbers are crazy](https://bun.sh/docs/api/websockets)) and `DB drivers`, though some are still in development. It's working on better Windows support and currently natively supports [SQLite](https://bun.sh/docs/api/sqlite), with plans for more database drivers.

## State of Bun

### For Frontend Devs

> As a frontend dev, its pretty stable and speed is just wow! 🤯

If you're a frontend developer, you can start using Bun instead of Node right away. Many frontend developers, myself included, have made the switch and provided positive feedback. Personally, I haven't encountered any issues so far. Frontend developers can make the transition with ease.

### For Backend Devs

> Test it properly before pushing the code to prod. Expect some unexpected bugs. 👀

For backend developers, Bun presents a new ecosystem, but the community is vibrant and energetic. Frameworks like [ElysiaJS](https://elysiajs.com/) and [Hono](https://hono.dev/) are showcasing impressive performance numbers, even competing with some Golang and Rust-based frameworks, which is remarkable! [Vercel's recent announcement of official support for Bun](https://vercel.com/changelog/bun-install-is-now-supported-with-zero-configuration) further validates its potential. While Bun claims to be production-ready, but do a thorough testing before you deploy to prod.

## Others

### Shoutout to Deno

[Deno](https://deno.com/) offers similar functionality to Bun and even provides frontend and backend frameworks, along with a cloud service for deploying Deno applications directly. The offerings of Bun and Deno share some similarities, so it's worth exploring if these capabilities excite you.

### Oven backed by VC?

Oven, the parent company of Bun, recently [secured $7M in funding](https://www.crunchbase.com/organization/oven/company_financials). While they operate independently, there might be discussions about their future revenue model. On the other hand, Node.js is part of the OpenJS Foundation. Many developers have expressed ([Reddit](https://www.reddit.com/r/javascript/comments/wwd11n/oven_the_company_behind_bun_gets_7m/)) different thoughts on this.

> My personal opinion is Good things come at a cost and many OSS tools were made possible because of investments from renowned companies and individuals, resulting in remarkable offerings like VS Code, React, and Next.js. Regarding licenses, Bun currently operates under the [MIT license](https://bun.sh/docs/project/licensing), which is favourable. `Though, I wish they also mention the same license (as license file) in github repo as well so community can be updated if they change it in near future`. Given Bun's impressive performance, it's worth giving it a try.

If you've made it this far, thank you so much for reading my blog. I'm thrilled to have you here! `Feel free to provide any type of feedback/report error`. I'll be back soon with more content. Until then, let's continue making

> The web a simpler and happier place together :)
