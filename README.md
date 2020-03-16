# Reproduction of `arrow-return-shorthand` to `arrow-body-style` incompatibility use-case

To reproduce the issue:
1. Install dependencies - `yarn install`
1. Check that TSLint passes - `yarn tslint --project tsconfig.json`
1. Run migration script - `npx tslint-to-eslint-config@0.5.1 --typescript tsconfig.json`
1. Run ESLint to see the error - `yarn eslint index.ts`

Extra files in `extra/` folder:
1. `.eslintrc.js` and `tslint-to-eslint-config.log` - committed to freeze the script result for reference
1. `npx.log` - contains result of migration script (from step 3 above + `> npx.log`), also for reference

You could also run `cmp {,extra/}.eslintrc.js` and `cmp {,extra/}tslint-to-eslint-config.log` to check that the produces output matches the files in `extra/` (empty stdout means success).
