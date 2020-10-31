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
  "compilerOptions": {
    "target": "esnext",
    "watch": true,
    "lib": ["dom", "es2017"]
  }
}
```

1.  `target`:  this is the flavor of javascript that your code will be compiled to
2.  `watch`: this will just recompile our code every time we save the file
3.  `lib`: which allows us to automatically include typings for certain environments, such as the DOM or ES2017, so if your building a web application, you'd like to include that dom library which allows typescript to compile your code with all with all the native DOM calsses without any compilation errors, for example if we go back to our code, we can use the URL class, which is part of the DOM, and we'll get autocomplete and intellisense, on this class, so this is where the incredible tone of typescript starts to come in 


```js
let lucky: any = 23;
let lucky: number = 23
```

`any`: (implicit) this just means that this variable can be assigned of any value, and the compiler won't check it

`number`: (explicit) 


**You can also create your types from**

```js
type Style = 'bold' | 'italic'

let font: Style
```

let's imagine we have 2 objects, and we wanna enforce this object shape to have first and last name with `string` types, we do this with `interface`

```js
interface Person {
  first: string;
  last: string;
}
```

now we can use this interface to strong this type objects directly, or we can use it as a return value from a function, or as an argument, or any urls in our code


another exmple:

```js
function pow(x:number, y:number): string {
  return Math.pow(x, y)
}
```

if you don't want to return some value, and you just want to have some side effects, in that case you can type your function return value to `void`, so you'll commonly see the `void` type on functions like `event listeners` or `side effects` that dont return a value

**The next thing we look at, is how to strong type of an array, so we start by creating an empty array, then pushing a few different values to a different types**

**we can force this array to only have `number` types by doing this, signifying that it's an array**

```js
const arr: number[] = []
```

now everytime you will get an error, every time we try to push a value that is not a number, this is specially useful when you work with an array of objects, and you wanna get some `intellisense` as you iterating over those objects, for example if you retrive an array of people of our database, we could use of our `Person Interface` to know the exact shapes of our objects as they retrieved.

```js
arr.push(1) => corret
arr.push('a') => incorrect
arr.push(false) => incorrect
```

```js
const arr: Person[] = []
```


### Generics in typescript

you may be in the situations internally inside of the class or function

so the `capital T` in this code represents a variable type that we can pass in to strong type this observable

```js
class Observable<T> {
  constructor(public value: T) {}
}
```

for example we might have an observable of a number, or maybe we have an observable of our Person interface and so on...

```js
let x: Observable<number>;

let y: Observable<Person>;
```

