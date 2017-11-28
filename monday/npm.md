# Welcome to the New `npm`
[slides](https://slides.com/seldo/welcome-to-the-new-npm)

## What is npm
1. client: the cli
1. registry: couchbase object store
1. website: package discovery
1. company: sells stuff
1. workflow: init, publish, etc.
1. community: who's building and using stuff

### npm's goal
** Reduce friction for JavaScript developers**

_`npm` just wants to get out of your way_

## What's New?

### the client
- npm 5 is 10x faster than npm 4
- npm 5 locks by default (package-lock.json produces perfectly reproducible builds, every time)
- When to use package-lock.json?
 - lock files are better for shipping than building
 - npm ignores lock as a lib
 - npm uses lock in git repos
- npm 5 saves by default
- npm 5 works offline: uses local cache when not connected
 - you can force npm to use only the cache `--offline`
 - you can bias to offline `--prefer-offline`
- [package.community](http://package.community/)

### the registry
- faster
 - requests are served 40% faster
 - metadata requests are 50% smaller
 - Downloads are up to 200% faster
 - constrained by processor speed
- 2FA
- [webhooks](go.npm.me/hooks)
- npm Organizations are free
- unpublish is restricted | use `npm deprecate` instead
- [new npm website](https://preview.npmjs.com)
 - GCU / Please Clap
- Search is better

### the company
- how do y'all make money?
 - sell services that make JavaScript developers more productive
 - npm Enterprise will make your giant corporation feel good about JavaScript

### the workflow
- run scripts
- lifecycle hooks: automate behavior
- `npx`: executes packages remotely and then tears down
 - `npx npm-check -u`: interactive update tool
 - `npx` runs dev dependencies
- `cipm`
 - is 2x faster than npm 5
 - cipm is 20x faster than npm 4
 - _soooooon_

## What's Next?
front end Modules
- the new stuff isn't any better than the old stuff
- we're going to need to build a bunch of terrible
