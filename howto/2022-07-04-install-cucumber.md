# How to add cucumber to a TS project?

Install dev dependencies:

    @cucumber/cucumber
    @cucumber/pretty-formatter
    cucumber-typescript-snippets
    ts-node

Add cucumber.js:

    const formatOptions = {
    snippetSyntax: 'cucumber-typescript-snippets/index.js',
    };

    let common = [
    'features/**/*.feature',
    '--require src/cucumber/**/*.ts',
    '--require-module ts-node/register',
    '--publish-quiet',
    `--format-options '${JSON.stringify(formatOptions)}'`,
    '--format @cucumber/pretty-formatter',
    ].join(' ');

    module.exports = {
    default: common,
    };

Make sure you have this in your tsconfig.json:

compilerOptions.target && compilerOptions.lib not less than es6

compileOptions.module should be "CommonJS"


## To make jestful assertions

we also need `expect` to be available in the scope which is in jes package

yarn add --dev ts-jest @types/jest jest

