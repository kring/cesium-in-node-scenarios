This project tests the ability to import Cesium modules from an npm package in various scenarios.

Change the Cesium package being tested in package.json.

Use `nvm` to switch your Node.js version then `npm install`:

To test on Node.js versions earlier than 12, run:

```
npm run test-old
```

The following tests are performed:

* `commonjs`: Loads Cesium using `require` from a source file that Node.js considers to be a CommonJS module. Cesium will automatically load `esm` to assist in loading its ES modules.
* `esm`: Loads Cesium using an `import` from an ES module loaded with `esm`.

To test Node.js versions 12+, run:

```
npm run test-new
```

In addition to the two `test-old` tests above, `test-new` also runs the following test:

* `es`: Loads Cesium using an `import` from a real actual ES module, using `--experimental-modules`.
