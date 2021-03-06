# Webpack

- [Webpack validator](https://github.com/js-dxtools/webpack-validator) - like eslint but for webpack

## Tree-shaking

- **babel preset 2016-webpack** will transpile the ES Modules instead of being transpiled in babel. 
- By delegating the ES Modules transpilation to webpack, webpack is able to run static analysis to see which modules are being used, hence optimize the bundle with tree-shaking. 
- CommonJS modules are not staticly analyzable.

## Code splitting

- Load modules using `Sistem.import()` and webpack will split that code and lazy load it.

## Hashing

- To optimize the browser's cache we can fingerprint the filenames with `chunkhash`
- [npm html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin) To point the html to the correct hashed bundle js 

## Separate bundle for common libraries

- CommonsChunkPlugin 

## Plugins

- DedupPlugin - removes duplicates in npm modules.
- LoaderOptionsPlugin - toggle minification and debugging, as well as other configs.
- DefinePlugin - parses `process.env.NODE_ENV` to a string, like **envify**
- UglifyJSPlugin - removes unused code and dev warnings. It can also discard polyfils for ie8. All of this helps to shrink the bundle size