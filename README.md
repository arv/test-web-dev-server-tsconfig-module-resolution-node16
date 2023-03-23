This is a test case for a bug in `@web/dev-server-esbuild`.

## Steps to reproduce

1. Clone the repo
2. Run `npm install`
3. Run `npx tsc --noEmit`

```
$ npx tsc --noEmit
node_modules/@web/dev-server/index.d.mts:2:15 - error TS2835: Relative import paths need explicit file extensions in EcmaScript imports when '--moduleResolution' is 'node16' or 'nodenext'. Did you mean './dist/index.js'?

2 export * from './dist/index';
                ~~~~~~~~~~~~~~

src/test.ts:2:35 - error TS7016: Could not find a declaration file for module '@web/dev-server-esbuild'. '/Users/arv/src/test-web-dev-server-tsconfig-module-resolution-node16/node_modules/@web/dev-server-esbuild/index.mjs' implicitly has an 'any' type.
  There are types at '/Users/arv/src/test-web-dev-server-tsconfig-module-resolution-node16/node_modules/@web/dev-server-esbuild/dist/index.d.ts', but this result could not be resolved when respecting package.json "exports". The '@web/dev-server-esbuild' library may need to update its package.json or typings.

2 import * as devServerEsbuild from '@web/dev-server-esbuild';
                                    ~~~~~~~~~~~~~~~~~~~~~~~~~


Found 2 errors in 2 files.

Errors  Files
     1  node_modules/@web/dev-server/index.d.mts:2
     1  src/test.ts:2
```
