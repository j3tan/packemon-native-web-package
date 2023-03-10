# Packemon Asset Test

Example showing that building a package that has a `.css` import fails because it tries to process the `bundled` file which includes a (probably incorrect?) path to `asset.css`

```js
// Bundled with Packemon: https://packemon.dev
// Platform: browser, Support: stable, Format: esm

import 'app.css';
function app() {
  console.log('app started');
}
export { app };
//# sourceMappingURL=index.js.map
```

causes:

```shell
 ERROR

 ENOENT: no such file or directory, copyfile '/path/to/packemon-asset-test/src/app.css' -> '/path/to/packemon-asset-test/assets/app-b4d03e96.css'

 STACK TRACE

Error: ENOENT: no such file or directory, copyfile '/path/to/packemon-asset-test/src/app.css' -> '/path/to/packemon-asset-test/assets/app-b4d03e96.css'

```


Run:
```shell
yarn build
```
