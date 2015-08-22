Redux HackerNews
================

A universal (isomorphic) Hacker News clone.

## Build with

- [React]
- [Redux]
- [React Router]
- [Babel]
- [ESLint]
- [Webpack]

Usage
-----

#### `npm run dev`
Runs the webpack build system just like in `compile` but enables HMR and react hot-loader. The webpack dev server can be found at `localhost:3000`.

#### `npm run dev:debug`
Same as `npm run dev` but enables `--debug` flag automatically (this will enable redux-devtools).

#### `npm run dev:quiet`
Same as `npm run dev` but disables verbose debugging information.

#### `npm run compile`
Runs the Webpack build system with your current NODE_ENV and compiles the application to disk (`~/dist`). Production builds will fail on eslint errors (but not on warnings).

**NOTE**: I'm still searching for a good solution for when to run the server entry point bundler, since it doesn't make much sense to run webpack on it when you're just using the dev server. As a result (only for the time being) if you wish to run the Koa server you'll need to run `compile` with `NODE_ENV=production` first, since that's the only time the server bundle gets compiled.

#### `npm run test`
Runs all tests for the application. When run in a production build, failing tests will fail your build.

#### `npm run test:unit`
Similar to `npm run test`, but only runs unit tests. In development mode this will run in watch mode and re-run individual test files when they change.

#### `npm run test:server`
Runs the small test suite in `~/server/scripts/test.js`. This will ideally be expanded in the future to instead act as an entry point similar to what exists for client-side tests.

#### `npm run server:start`
Kicks off the Koa server (defaults to `localhost:4000`).

#### `npm run deploy`
Helper script to run tests and then, on success, compile your application. Server tests that rely on the compiled server bundle will be run after compilation finishes.


Thanks
------

High inspired by those projects:

- [erikas/react-redux-universal-hot-example](https://github.com/erikras/react-redux-universal-hot-example)
- [davezuko/react-redux-starter-kit](https://github.com/davezuko/react-redux-starter-kit)

License
-------

MIT
