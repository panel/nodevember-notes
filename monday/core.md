# State of Node.js Core

## LTS Schedule
- [Schedule](https://github.com/nodejs/Release)
- April is even numbered: Current (2 mo) -> Active LTS (18 mo) -> Maintanance (12 mo)
- October is odd numbered: Current (6 mo) -> Maintanance (2 mo).

## Nodejs 8.x
- Released 5/30/17
- Pushed back due to V8 discussion

## Tracking v8
- v8 moves very fast. 6 week release cycle.
- Chrome is evergreen; node is not
- Must be considered when planning Node's LTS
- Node is a first class citizen in V8
- More collaboration between V8 and Node.

## A New Compiler Pipeline
- V8 5.9 enabled Ignition + [TurboFan](https://github.com/v8/v8/wiki/TurboFan) by default (Node 8.3.0)
- No more optimization killers
- `try-catch-finally` and `async` functions fully optimizable
- Code optimized for Crankshaft will need to be revisited

## Node 8 LTS
- Codnamed Carbon
- First LTS line with native `async`/`await`
- First LTS line with WebAssembly
- Current EOL scheduled for 12/31/2019

### Exciting Features
- TurboFan
- N-API*
- HTTP2*
- Inspector*
- `util.promisify()`
- ECMAScript Modules*
- Async Hooks*
- `fs.copyFile()`
- Performance Timing API*
- `util.callbackify()`

*Experimental

## Nodejs 9.x
- Semver major releases are (should be) boring
- Also released 10/2017
- Error code migration continues
- HTTP 400 on malformed request
- Timers now ward on overflow
- `assert` can throw any type of error

### Other New Features
- `util.isDeepStrictEqual()`
- `fs.realpath.native()`
- `process.ppid`
- Configurable paths with `require.resolve()`
- Soon: top level `await` in REPL

### Improved Language Support
- Node 9 will support roughly all of ES2015-2018
- Adopt new language features cautiously

## Picking a Version for Production
- Is Node Mission critical?
- Do you require stability?
- Can you update Node easily/frequently?
- Do you **need** the latest Features

## Example "Current" Regressions
- `zlib` regression
- `readline`

## Improved Testing
- Over 2100 tests run on CI on every commit

## VM Neutrality
- Historically only V8
- There are many other JS runtimes
- Constrained envs may prefer non-v8

## Node on Chakra
- CharkaCore powers MS Edge's JS engine
- nodejs/node-chakracore is Node on CharkaCore
- Repsonsible for a lot of N-API work

## Node.js Security Working Group
- Eventual goal to coordinate core and npm vulnerabilities

## Increased Focus on Diagnostics
- Inspector Modules
- node-report
- llnode, mdb_v8

## Possible New Features
- Works
- Another New Streams API
- Promisified Core API
