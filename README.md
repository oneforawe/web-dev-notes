# Web Dev Notes

Notes on web-development options and decisions.

Main interests (as of 2024-02-08):

* React (or Preact)
  * node (w/ nvm) + pnpm + (next or vite/wmr) + (p)react + etc
  * deno + (?) + vite(/fresh) + (p)react + etc
* Solid
  * node (w/ nvm) + pnpm + vite(?) + solid + etc
  * deno + (?) + vite(?) + solid + etc

## Dev Concepts

* content, style, interactivity/reactivity (static vs dynamic)
  * html, css, javascript, typescript, etc
* composition:
  components
* state control:
  store/redux, nano-store(?)
* reactivity:
* performance / compilation /
  [rendering](https://www.patterns.dev/vanilla/rendering-patterns):
  static site generation (SSG), static rendering,
  client-side rendering (CSR), server-side rendering (SSR),
  [islands](https://www.patterns.dev/vanilla/islands-architecture),
  bundle-splitting,

## Pieces of Tech

### Runtimes+

Maybe stick with Node; Deno looks like it may not be stable enough yet, but it
could be ready, so investigate more; Bun will likely be rejected at work for no
native-Windows version.  Also, Bun's advantages might be superficial /
[hype](https://dev.to/thejaredwilcurt/bun-hype-how-we-learned-nothing-from-yarn-2n3j).

* [node](https://nodejs.org/en) - pop status quo
* [deno](https://deno.com/) - secure, faster
  * Usage:  
    Used by [slack](https://api.slack.com/automation/security) and
    [others](https://deno.com/blog?tag=partnerships), to some degree at least.
  * Security:  
    "Node.js isn’t far behind on this front. Node.js 20 introduced a permissions
    model allowing similar security aspects as those of Deno."
    -[Snyk](https://snyk.io/blog/javascript-runtime-compare-node-deno-bun/)
  * Stability:  
    "However, not all of Deno's features are ready for production yet."  
    "Deno's standard modules (<https://deno.land/std>) are not yet stable."  
    -From [docs](https://docs.deno.com/runtime/manual/runtime/stability)
  * However:  
    As an experienced friend of mine said: "[Having unstable features] is pretty
    much standard for everything. There are unstable features in node. How
    important they are for what you are working on will vary."
* [bun](https://bun.sh/) - fast (runtime & toolkit) -- if Windows, only WSL

### Package Managers

Maybe stay near npm and use pnpm instead.

* [npm](https://nodejs.org/en/learn/getting-started/an-introduction-to-the-npm-package-manager) -
  status quo (with [registry](https://docs.npmjs.com/about-npm))
* [pnpm](https://pnpm.io/) - [performant](https://pnpm.io/faq#what-does-pnpm-stand-for) npm
* [yarn](https://classic.yarnpkg.com/en/)
* [bit](https://bit.dev/)
* [bun](https://bun.sh/) is (also) an npm-compatible package manager.

### Frontend Frameworks

Maybe Solid. Maybe stick with React, but then consider Preact.

For interactivity / reactivity. Considering JavaScript/TypeScript-based
frameworks:

* [htmx](https://www.htmx.org/) - interactivity via new html attributes
* [React](https://react.dev/) - pop status quo
* [Preact](https://preactjs.com/) - ~lighter-weight React
  (provides the thinnest possible Virtual DOM abstraction on top of the DOM)
* [Solid](https://www.solidjs.com/) - similar to React but new paradigms
  (doesn't have a Virtual DOM)
* [Svelte](https://svelte.dev/) (framework/compiler)
* [Lit](https://lit.dev/)

Others: Angular, Vue, Qwik, Alpine

Python: Django; Ruby: (Ruby on) Rails; Elixir: Phoenix;

### Build/Deploy Toolkits and Frameworks

Maybe use Next, Vite/WMR/Fresh, or Remix.

* [create-react-app](https://legacy.reactjs.org/docs/create-a-new-react-app.html) -
  legacy / old status quo (aka CRA)
* [new react create](https://react.dev/learn/start-a-new-react-project) - ~4
  recommendations (Next, Remix, Gatsby, Expo)
* Meta-Frameworks(?)
  * [Next](https://nextjs.org/)
  * [Remix](https://remix.run/)
  * [Gatsby](https://www.gatsbyjs.com/)
  * [Expo](https://expo.dev/)
* [vite](https://vitejs.dev/) - ~closest analog to CRA (but only basic bundling/code-splitting?)  
  See [Keynote: The State of Vite | ViteConf 2023](https://www.youtube.com/watch?v=hrdwQHoAp0M&t=14m16s)
* [wmr](https://github.com/preactjs/wmr) - for preact
* [fresh](https://fresh.deno.dev/docs/introduction) - (deno + fresh + preact)
* [SvelteKit](https://kit.svelte.dev/) (Svelte+Vite)

Others: [Astro](https://astro.build/) (for content-driven sites), Fresh, Lume?

### Style

I advocate just using SCSS and not tailwind.

* [sass](https://sass-lang.com/) - Syntactically Awesome Style Sheets
  (original indented syntax, .sass; newer SCSS / Sassy CSS syntax, .scss)
* [tailwind](https://tailwindcss.com/)

### Frontend Toolkits/Libraries

Use shadcn, radix-ui!

For components, styling, utilities, etc.

* [shadcn/ui](https://ui.shadcn.com/) - build-your-own library (see
  [here](https://www.youtube.com/watch?v=2Q0mWH6g8Fo))
* [v0.dev](https://v0.dev/) - ai ui generation
* [radix-ui](https://www.radix-ui.com/) -
  primitives for accessible React components
* [tailwind-ui](https://tailwindui.com/)
* [mui](https://mui.com/material-ui/) - Material UI
* [bootstrap](https://getbootstrap.com/)

Not too bad to use mui or maybe bootstrap where helpful, but shadcn/shadcn looks best!

### DevOps / CI/CD

Investigate more.

* [Nx](https://nx.dev/)
  Nx is a build system with built-in tooling and advanced CI capabilities. It
  helps you maintain and scale monorepos, both locally and on CI.

## Combinations of Tech

(React+Next) ~ (Vue+Nuxt) ~ (Svelte+SvelteKit)

* Node
  * React + CRA - legacy
  * React + Vite
  * React + Next
  * React + Remix
  * Solid + Vite
  * Solid + ?
* Deno
  * [Fresh](https://fresh.deno.dev/) - framework
  * [Aleph](https://alephjs.org/)
  * [Lume](https://lume.land/) - SSG
* Bun
  * React (+ framework ?)
  * Solid (+ Vite/etc?)
  * [BETH](https://www.youtube.com/watch?v=cpzowDDJj24) stack -
    bun + elysia + [turso](https://turso.tech/) + htmx
