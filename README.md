# Broken Parcel Build

1. Run `npm run build`
2. Run `cd dist && npx serve`
3. Open local server URL
4. Open console and reload, see error `Uncaught SyntaxError: Cannot use 'import.meta' outside a module`

The reason the error occurs is because the `script` tag is missing `type="module"`.

To fix, remove the `browserslist` entry in `package.json`, which only generates a single bundle for modern browsers. Repeat the build and see that the single script tag does have `type="module"` and no error occurs.
