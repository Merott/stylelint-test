This is to demonstrate an issue, where `stylelint` won't lint CSS files in nested directories.

Clone the repo and run `npm install`. Then:

- Run `./node_modules/.bin/stylelint **/*.css` (2 will be reported to have lint errors):

  ```
  src/nested/styles-nested.css
  3:3   ✖  Unexpected empty line before declaration                   declaration-empty-line-before
  4:19  ✖  Expected newline after ":" with a multi-line declaration   declaration-colon-newline-after

  src/styles.css
  3:3   ✖  Unexpected empty line before declaration                   declaration-empty-line-before
  4:19  ✖  Expected newline after ":" with a multi-line declaration   declaration-colon-newline-after
  ```

- Run `npm run lint` (only 1 file will be reported to have lint errors)

  ```
  src/styles.css
  3:3   ✖  Unexpected empty line before declaration                   declaration-empty-line-before
  4:19  ✖  Expected newline after ":" with a multi-line declaration   declaration-colon-newline-after
  ```
