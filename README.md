# Yet Another Node.js ES2015 boilerplate

This is a yet another ES2015 boilerplate, this time specifically designed for writing code server-side with Node.js.

Everything Javascript related is configured in the `package.json`. I prefer this than 45 million files in the root of a new project. This includes building the project all managed with `npm` scripts rather than some independent runner.

## What You Get

- Compilation from ES2015 to ES5 using [Babel](https://babeljs.io/) of course.
- [ESLint](http://eslint.org/) with Airbnb's [popular configuration](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb) as default. The configuration lines in `package.json` make sure that it works without deprecation messages in the very latest ESLint.
- [ava](https://github.com/sindresorhus/ava) for testing with ES2015 support. A very fast parallel test runner with a minimalist approach that recalls [tape](https://github.com/substack/tape). I like `tape` because it doesn't throw loads of globals around and require an independent runner.
- [sinon](https://github.com/sinonjs/sinon) for mocking in tests. You'll pretty much always need this pretty quickly.
- [nyc](https://github.com/bcoe/nyc) for code coverage.
- [Ramda](http://ramdajs.com/), a functional JS library which I use all the time.
- A build on [Travis](https://travis-ci.org/) by default.

## What You Can Do

- All the usual `npm` commands you might expect are here. `npm start`, `npm watch` and so on.
- `npm run test:watch` runs the tests on a watch. Its particularly brutal as it runs the linter before the tests and fails if the linter fails. This is a personal preference which means using JS feels a lot more strict, where mistakes or weirdnesses don't even work. A useful practice to get into.
- `npm run lint` runs ESLint.
- `npm run clean` removes the compiled ES5 in the `lib/` directory.
- `npm run watch` runs the code on a watch. Useful for just hacking about.
- `npm run cover` runs the coverage check.
- `npm run check-coverage` runs the coverage check and fails entirely if not at a certain threshold. I set this at 100% but around 85% seems to me wise for any real project.

## TODO

- Make additional lines in the configuration of ESLint no longer required.
- Some sort of documentation and type checker.
  - I like minimalist functional style type signatures over JSDoc nightmares where the documentation can be longer than the code.
  - You want to be able to understand the inputs and outputs in seconds and a well named function should describe what it is up to.
  - [Rtype](https://github.com/ericelliott/rtype) and its library [rfx](https://github.com/ericelliott/rfx) does this with objects you embed into code. The advantage is this allows validation at runtime.
  - [jsig](https://github.com/jsigbiz/spec) does much the same, but with comments as opposed to strings in code. No runtime checking.
  - Naturally there is [talk of them merging](https://github.com/ericelliott/rtype/issues/47).
  - Both are in developer preview but `jsig` edges it by being something simple I could just use and get on with my life. Just comments in a natural format.
  - Facebook's [Flow](http://flowtype.org/) is also a thing. The disadvantage of Flow as well as something like TypeScript is you actually aren't writing functional Javascript anymore. Then again we got over this for using JSX in React so maybe it is fine. But it checks types for you which prevents coding mistakes as you are working.
- Use [Cookie Cutter](https://github.com/audreyr/cookiecutter) or something to make a new project generator using this template.
