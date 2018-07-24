# node-inline-cpp
Inline C++ with Node.js

## Usage

```js
// test.js

const compile = require('inline-cpp');

const Hello = compile `
  String func(const CallbackInfo& info) {
    return String::New(info.Env(), "Hello");
  }
`

const World = compile `
  String func(const CallbackInfo& info) {
    return String::New(info.Env(), "World!");
  }
`

console.log(Hello(), World())
```

```sh
➜ node test.js
Hello World!
```
