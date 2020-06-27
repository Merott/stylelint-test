This is to demonstrate an issue, where `stylelint` won't lint all CSS files when run as an NPM script.

Clone the repo and run `npm install`. Then:

- Run `./node_modules/.bin/stylelint **/*.css` (3 CSS files will be reported to have lint errors):

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

- Run `npm run lint` (only `src/styles.css` will have lint errors reported)

  ```
  src/styles.css
  3:3   ✖  Unexpected empty line before declaration                   declaration-empty-line-before
  4:19  ✖  Expected newline after ":" with a multi-line declaration   declaration-colon-newline-after
  ```
