# Cypress + cypress-cucumber-preprocessor + Currents

Example of using `cypress-cucumber-preprocessor` with Currents.

- Use [`@currents/cli`](https://www.npmjs.com/package/@currents/cli) package to use Currents.dev as an alternative dashboard for ochestrating and reporting of cypress tests.
- Using `@currents/cli` allows using `npx currents` instead of `npx cypress`. Unfortunately `cypress-cucumber-preprocessor` has the `cypress` command hardcoded in its code, that's why an additional step is required to "patch" `cypress-cucumber-preprocessor` and use `currents` instead of `cypress`:
  - the patch is in `patches` directory (it just replaces `cypress` command with `currents`)
  - to apply the patch manually run `npx patch-package`. Read more about [`patch-package`](https://www.npmjs.com/package/patch-package).
  - to apply the patch automatically as part of `npm install` add `"postinstall": "patch-package"` to `package.json:scripts`

When patched, you can use `cypress-tags` command as usual, for example:

Note: get the record key and the project id at https://app.currents.dev
