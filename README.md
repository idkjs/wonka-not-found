# Steps to repoduce error

## Setup Project

Dependencies have been installed with `pnpm`.

```sh
pnmp i bs-webapi wonka
```

Add new deps to `bsconfig.json`:

```json
  "bs-dependencies": [
    "wonka",
    "reason-react",
    "bs-webapi"
  ],
```

## Run Project

```sh
npm install
npm start
```

On running `npm start` compiler error is:

```sh
➜  wonka-not-found npm start

> wonka-not-found@0.1.0 start /Users/prisc_000/Downloads/wonka-not-found
> bsb -make-world -w -ws _

bsb: no work to do.
bsb: no work to do.
File "bsconfig.json", line 1
Error: package gentype not found or built
- Did you install it?
- If you did, did you run `bsb -make-world`?
>>>> Start compiling
[18/25] Building src/Blinking...ClickEventDemo-ReasonReactExamples.cmj
FAILED: src/BlinkingGreeting/WonkaClickEventDemo-ReasonReactExamples.cmj src/BlinkingGreeting/WonkaClickEventDemo-ReasonReactExamples.cmi /Users/prisc_000/Downloads/wonka-not-found/src/BlinkingGreeting/WonkaClickEventDemo.bs.js
/Users/prisc_000/.fnm/node-versions/v13.3.0/installation/pnpm-global/3/node_modules/.pnpm/registry.npmjs.org/bs-platform/7.0.2-dev.1/node_modules/bs-platform/lib/bsc.exe -nostdlib -bs-package-name reason-react-examples -bs-ns ReasonReactExamples  -bs-package-output commonjs:src/BlinkingGreeting -color always -bs-suffix -I . -I src/ReducerFromReactJSDocs -I src/ReasonUsingJSUsingReason -I src/BlinkingGreeting -I src/FetchedDogPictures -I src -I /Users/prisc_000/Downloads/wonka-not-found/node_modules/reason-react/lib/ocaml -I /Users/prisc_000/Downloads/wonka-not-found/node_modules/bs-webapi/lib/ocaml -I /Users/prisc_000/Downloads/wonka-not-found/node_modules/wonka/lib/ocaml -I /Users/prisc_000/Downloads/wonka-not-found/node_modules/bs-platform/lib/ocaml -w -30-40+6+7+27+32..39+44+45+101 -bs-super-errors -bs-no-version-header -o src/BlinkingGreeting/WonkaClickEventDemo-ReasonReactExamples.cmj src/BlinkingGreeting/WonkaClickEventDemo.reast

  We've found a bug for you!
  /Users/prisc_000/Downloads/wonka-not-found/src/BlinkingGreeting/WonkaClickEventDemo.re 5:6-10

  3 │    fromEvent(document, 'click').subscribe(() => console.log('Clicked!')
      ); */
  4 │ open Webapi.Dom;
  5 │ open Wonka;
  6 │ [@react.component]
  7 │ let make = () => {

  The module or file Wonka can't be found.
  - If it's a third-party dependency:
    - Did you list it in bsconfig.json?
    - Did you run `bsb` instead of `bsb -make-world`
      (latter builds third-parties)?
  - Did you include the file's directory in bsconfig.json?

[23/25] Building src/FetchedD...hedDogPictures-ReasonReactExamples.cmj
FAILED: subcommand failed.
>>>> Finish compiling(exit: 1)
```
