# Webpack breaks the code in production mode

## Repro steps

- webpack": 4.11.1

1. `git clone https://github.com/mysticatea/webpack-issue.git`
2. `cd webpack-issue`
3. `npm it`

## Details

- The source code: [src/index.js](./src/index.js)
- The result code: [dist/main.js](./dist/main.js)

The result code contains a re-assignment to a `const` variable.

```js
const r=e[t];(r=r).fatal||r.ruleId||!r.message.includes("eslint-disable")||console.log(r)
```

It looks like a confusion about inlining local functions.
