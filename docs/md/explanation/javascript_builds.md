# JavaScript Builds

Perspective requires the browser to have access to Perspective's `.wasm`
binaries _in addition_ to the bundled `.js` files, and as a result the build
process requires a few extra steps. To ease integration, Perspective's NPM
releases come with multiple prebuilt configurations.

## Browser

### ESM Builds

The recommended builds for production use are packaged as ES Modules and require
a _bootstrapping_ step in order to acquire the `.wasm` binaries and initialize
Perspective's JavaScript with them. However, because they have no hard-coded
dependencies on the `.wasm` paths, they are ideal for use with JavaScript
bundlers such as ESBuild, Rollup, Vite or Webpack.

### CDN Builds <!-- Explanation -->

Perspective's CDN builds are good for non-bundled scenarios, such as importing
directly from a `<script>` tag with a browser-side `import`. CDN builds _do not_
require _bootstrapping_ the WebAssembly binaries, but they also generally _do
not_ work with bundlers such as `WebPack`.


## Node.js

There is a Node.js build as well for `@finos/perspective` data engine, which
shouldn't require any special instructions to use.
