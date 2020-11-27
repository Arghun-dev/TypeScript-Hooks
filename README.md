# TypeScript-Hooks

**useful links**
`
https://blog.logrocket.com/how-to-use-react-context-with-typescript/
`

### What us TypeScipt?

1. Open source programming language
2. Developed and maintained by microsoft
3. A superset of javascript (like C++ to C)
4. Brings static typing to javascript


### some Typescript examples

1.
```js
function sum (a:number, b:number): number {
  return a + b;
}

let arr:[number, string, boolean] = [12, 'arghun', true]

let arr:any = [1, 'string', true]

function test(): void {
  console.log('this function does not return anything')
}
```


2.
```js
import React, { useState } from 'react'

type FormElm = React.FormEvent<HTMLFormElement>

interface ITodo {
  text: string
  complete: boolean
}

export default function Index() {
  const [count, setCount] = useState<number>(0)
  const [todos, setTodos] = useState<ITodo[]>([])
  
  const addNewTodo = (text: string) => {
     const newTodos: ITodo[] = [...todos, { text, complete:false }]
     setTodos(newTodos)
  }
  
  // this function is void type because it's not returnin anything
  const handleSubmit = (e:FormElm): void => {
    e.preventDefalt()
    setCount(0)
  }
  
  return (
    <form onSubmit={handleSubmit}>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>increase</button>
    </form>
  )
}
```

### Typescript has 12 basic types

`boolean`, 
`number`, 
`string`, 
`array` => 
`tuple` => [string, number, number]
`enum` => Outcome {Win, Lose, Draw}
`any` => Dynamic Type (like normal js)
`void` => a function that doesn't return
`null` => something does not exit
`undefined` => unassigned variable
`never` => function that never return
`object` => non-primitive 

### install typescript globally

`
$. npm i -g typescript
`


### create typescript project in react

`
$. npx create-react-app --template=typescript
`

## Create a Todo App using `TypeScript` and `Context`

1.
`
$. npx create-react-app todoapp --template=typescript
`


2. next let's structure your project as follow:

`
├
── src

|  ├── components

|  |    ├── AddTodo.tsx

|  |    └── Todo.tsx

|  ├── containers

|  |    └── Todos.tsx

|  ├── context

|  |    └── todoContext.tsx

|  ├── App.tsx

|  ├── index.css

|  ├── index.tsx

|  ├── react-app-env.d.ts

|  └── type.d.ts

├── tsconfig.json

├── package.json

└── yarn.lock
`
