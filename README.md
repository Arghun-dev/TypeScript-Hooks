# TypeScript-Hooks

### install typescript globally

`
$. npm i -g typescript
`


### create typescript project in react

`
$. npx create-react-app --template=typescript
`


typescript on it's own can't run anywhere, it won't work in the browser or node.js or anywhere, what we use, is that we use typescript compiler, to convert that typescript code, to vanilla javascript

**By default typescript will compile to ES3, which doesn't have support for `async await` so let's see what will happen when we write an async await function in our `ts` file and the compile it**

**So you'll notice here that our code gets transpiled to this crazy looking javascript, just so we can use async await in our main typescript, the compiler is actually sophisticated, and there is a ton of different options, that you can pass to it, to customize it's behaviour**

**The standard way of doing this is, to create a `tsconfig.json` file**


tsconfig.json
```js
{
  
}
```

1.  `target`:  this is the flavor of javascript that your code will be compiled to
2.  `watch`: this will just recompile our code every time we save the file
3.  `lib`: which allows us to automatically include typings for certain environments, such as the DOM or ES2017, so if your building a web application, you'd like to include that dom library which allows typescript to compile your code with all with all the native DOM calsses without any compilation errors, for example if we go back to our code, we can use the URL class, which is part of the DOM, and we'll get autocomplete and intellisense, on this class, so this is where the incredible tone of typescript starts to come in 
