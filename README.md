Reproducible test case of a Parcel v2 bug where the order of included modules with included scripts matters even though their contents is identical.

The `indexa.html` file uses order a,b and `indexb.html` uses order b,a for the script includes. `indexb.html` shows an error:

```
indexb.1d7bdfbc.js:1 Uncaught Error: Cannot find module '5CNsl'
    at n (indexb.1d7bdfbc.js:1:355)
    at b.js:1:1
```

To build:

`yarn parcel build indexa.html --public-url . --dist-dir docs/`
