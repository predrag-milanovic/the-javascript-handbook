# Bundlers

[Bundlers](https://webpack.js.org/concepts/) are tools that take your code from the way you write it to the way you want to ship it.

That matters because modern applications are usually made up of many files and dependencies. During development, that structure keeps things manageable. In production, though, you often want to deliver something much smaller and simpler to the browser, such as one bundle for the whole app or one bundle per page.

Popular bundlers do more than just bundle code. They often handle:

- Bundling: combining many files into one or a few output files.
- Minification: shrinking code by removing unnecessary whitespace and other extras.
- Code splitting: breaking an application into smaller chunks that can be loaded on demand.
- Tree shaking: removing unused code from the final bundle.
- Asset optimization: processing images, fonts, and other assets so they are smaller or better suited for production.
- Source maps: generating files that let you debug the bundled code as if you were still working with the original source.

For a long time, [Webpack](https://webpack.js.org/) was the default choice for front-end bundling, and it is still widely used. More recently, [Vite](https://vite.dev/) has become very popular because it is fast and usually much easier to configure. Vite is built on top of [Rollup](https://rollupjs.org/), which is another well-known bundler often used for production builds.

The main idea is simple: bundlers help you write code in a modular, maintainable way while serving it in a format that is smaller, faster, and better optimized for the browser.
