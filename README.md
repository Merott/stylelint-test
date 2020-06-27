This is to demonstrate this stylelint issue: https://github.com/stylelint/stylelint/issues/4846

The issue is that `stylelint` won't lint all CSS files when run as an NPM script, but it does if run directly.

1. Clone the repo and run `npm install`

2. Run `./node_modules/.bin/stylelint **/*.css` (3 CSS files will be reported to have lint errors):

  ```
  src/nested/styles-nested.css
  3:3   ✖  Unexpected empty line before declaration                   declaration-empty-line-before
  4:19  ✖  Expected newline after ":" with a multi-line declaration   declaration-colon-newline-after

  src/styles.css
  3:3   ✖  Unexpected empty line before declaration                   declaration-empty-line-before
  4:19  ✖  Expected newline after ":" with a multi-line declaration   declaration-colon-newline-after

  styles-top.css
  3:3   ✖  Unexpected empty line before declaration                   declaration-empty-line-before
  4:19  ✖  Expected newline after ":" with a multi-line declaration   declaration-colon-newline-after
  ```

3. Run `npm run lint` (only `src/styles.css` will have lint errors reported)

  ```
  src/styles.css
  3:3   ✖  Unexpected empty line before declaration                   declaration-empty-line-before
  4:19  ✖  Expected newline after ":" with a multi-line declaration   declaration-colon-newline-after
  ```
