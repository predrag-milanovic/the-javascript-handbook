# JavaScript Runtimes

A runtime environment is the platform where your JavaScript program executes. Your choice of runtime determines crucial aspects of your development:

- **Available APIs** — What functionality your code can access (`fetch`, `canvas`, file system, etc.)
- **Execution Model** — How code runs (JIT compiled vs interpreted)
- **Production Dependencies** — What you need to deploy
- **Deployment Target** — Backend (server), frontend (browser, mobile app), or both

## Common Runtimes

- [**The Browser**](https://developer.chrome.com/docs/devtools/console/javascript/) — The original JavaScript runtime (note: different browsers are technically different runtimes with varying implementations)
- [**Node.js**](https://nodejs.org/en/) — The most established server-side runtime
- [**Web Workers**](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers) — Isolated JavaScript execution within a browser
- [**Deno**](https://deno.com/) — A modern, secure server-side runtime with built-in TypeScript support
- [**Bun**](https://bun.sh/) — A newer, high-performance runtime written in Zig

## A Brief History

Originally, JavaScript only ran in browsers. Today, it runs almost everywhere—servers, mobile apps, desktop applications, and more.

## Choosing a Runtime

### Frontend Development

If you're building frontend web applications, your choice is made for you: **the browser**. However, you'll typically need to support multiple browsers, so understanding the API differences between Chrome, Firefox, Safari, and Edge is essential.

### Backend Development

Backend development gives you options:

- **Node.js** — The most mature and widely adopted. Massive ecosystem of packages via npm. Industry standard.
- **Deno** — Newer with better security defaults and native TypeScript support. Still growing.
- **Bun** — Newer with excellent performance claims and built-in bundling. Rapidly improving but less battle-tested.

## The Good News

All three backend runtimes are very similar to work with. You don't need to "learn" a runtime—if you understand JavaScript, you can work with any of them. The fundamentals remain the same; only the available APIs differ.

Choose based on your project needs, team expertise, and ecosystem maturity. For most teams, **Node.js remains the safe, proven choice**.
