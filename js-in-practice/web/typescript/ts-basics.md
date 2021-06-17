[Types tutorial](https://2ality.com/2018/04/type-notation-typescript.html)

Stick to --strict settings, as it gives all the typescript benefits

Type notation
let x: number;
X here is initialized as undefined, but TS won't let us read it before we assign it a value

Type Interface
// %inferred-type: number
We can also infer a type: `let anumber = 213`

type aliases
type Age = number
const age: Age = 32

Array types
Arrays have two roles in js: Lists (variabl length, same element type) and tuple (fixed length, possible different elements types)

Arrays as lists
TS can't determine the types of elements in an empty array, so we need to declare it
```
let arr: number[] = []
let arr: array<number> = [];
```

Arrays as tuples
If we are storing data like coordinates/2d points, we're using arrays as tuples. We need specific annotation because TS infers LIST types, not TUPLE types

```
let point: [number, number] = [5, 5];
```

Function types

A basic example that accepts a single number and returns a string:

(num: number) => string

We can use this type in a type annotation (not the function type after the function name):
```
const func: (num: number) => string = 
  (num: number) => String(num)
```
We don't need a type annotation tfor this example because TS is can infer function types

```
const func = (num: number) ==> String(num)
```

A more complicated version: 
```
function doStringify(callback: (num: number) => string){
  return callback(505)
}
```

void
void is a special result type for function that tells TS the function always returns undefined whether by not returning anything or explicitly having a undefined return

Option params

```
function doStringify(callback?: (num: number) => string){
   if (callback === undefined) {
    callback = String;
  }
  return callback(505)
}
```

TS parameter defaults
Default values make params optional. TS can infer types, but we can also specify them.
```
function createPoint(x=0, y=0): [number, number] {
  return [x, y];
}

function createPoint(x:number = 0, y:number = 0): [number, number] {
  return [x, y];
}
```

Rest Params

function joinNumbers(...nums: number[]): string {
  return nums.join('-');
}