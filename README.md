# Yarn 2 TailwindCSS Installation Bug

## Steps to repro

```
// https://create-react-app.dev/docs/getting-started
$ npx create-react-app my-app
$ cd my-app
$ yarn build
// Update to v2 of Yarn
$ yarn set version berry
$ echo "nodeLinker: node-modules" >> .yarnrc.yml
// so far so good
// Try to install TailwindCSS compat build
// https://tailwindcss.com/docs/guides/create-react-app#install-tailwind-via-npm
$ yarn add tailwindcss@npm:@tailwindcss/postcss7-compat
➤ YN0000: ┌ Resolution step
➤ YN0001: │ Error: tailwindcss@npm:@tailwindcss/postcss7-compat isn't supported by any available resolver
    at n.getResolverByDescriptor (/Users/someone/a-react-app/.yarn/releases/yarn-berry.cjs:2:336683)
    at n.bindDescriptor (/Users/someone/a-react-app/.yarn/releases/yarn-berry.cjs:2:336048)
    at d (/Users/someone/a-react-app/.yarn/releases/yarn-berry.cjs:2:357409)
    at async Promise.all (index 0)
    at async ie.resolveEverything (/Users/someone/a-react-app/.yarn/releases/yarn-berry.cjs:2:358614)
    at async /Users/someone/a-react-app/.yarn/releases/yarn-berry.cjs:2:377271
    at async f.startTimerPromise (/Users/someone/a-react-app/.yarn/releases/yarn-berry.cjs:2:389740)
    at async ie.install (/Users/someone/a-react-app/.yarn/releases/yarn-berry.cjs:2:377210)
    at async /Users/someone/a-react-app/.yarn/releases/yarn-berry.cjs:2:33217
    at async Function.start (/Users/someone/a-react-app/.yarn/releases/yarn-berry.cjs:2:388437)
➤ YN0000: └ Completed
➤ YN0000: Failed with errors in 0s 110ms
```

## Info

Node info

```
$ node --version
v14.15.4
```

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).
