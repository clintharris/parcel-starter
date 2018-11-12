### What is this?

An experiment with using Parcel.

### Dependency Notes

 - `parcel-bundler` allows us to use [Parcel](https://parceljs.org) to transpile and bundle the app. It comes with Babel.
 - `typescript` will transpile our TypeScript (`.ts` and `.tsx` files) to JavaScript. It is automatically used by Parcel.
 - [`babel-plugin-module-resolver`](https://github.com/tleunen/babel-plugin-module-resolver#readme) augments Babel's ability to import _JavaScript_ modules via path aliases (e.g., `import Foo from '@src/Foo'`). You have to configure the path aliases in `.babelrc`.
 - [`postcss-modules`](https://github.com/css-modules/postcss-modules) is automatically used by Parcel to enable [CSS Modules](https://github.com/css-modules/css-modules). Note that it is configured via the the [Parcel-specific](https://en.parceljs.org/transforms.html#postcss) `.postcssrc` config file. Also note that we have a `types.d.ts` file that declares `.scss` files as modules to prevent TypeScript errors when we try to `import stuff from 'somefile.scss'` (i.e., treat an `.scss` file as a module).
 - [`autoprefixer`](https://github.com/postcss/autoprefixer) is automatically used by `postcss-modules` to add browser-specific selector prefixes to CSS files, per configuration in `.postcssrc`.
 - [`node-sass`](https://github.com/