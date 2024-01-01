# vitest-monocart-coverage
> Generating native V8 coverage report for [Vitest](https://github.com/vitest-dev/vitest) with [Monocart coverage reports](https://github.com/cenfun/monocart-coverage-reports)

## Install
```sh
npm i vitest-monocart-coverage -D
```

## Vitest Config
```js
// vitest.config.js
import { defineConfig } from 'vitest/config';

export default defineConfig({
    test: {
        include: ['test/*.test.js'],
        coverage: {
            enabled: true,
            include: ['src/**'],
            provider: 'custom',
            customProviderModule: 'vitest-monocart-coverage',
            customProviderOptions: {
                // https://github.com/cenfun/monocart-coverage-reports?#default-options
                // logging: 'debug',
                reports: [
                    ['v8'],
                    ['v8-json']
                ],
                lcov: true,
                outputDir: 'coverage'
            }
        }
    }
});
```
see Vitest [Custom Coverage Provider](https://vitest.dev/guide/coverage.html#custom-coverage-provider)
