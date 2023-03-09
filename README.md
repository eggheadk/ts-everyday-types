# Typescript


## 1. Everyday Types

### `string, number, boolean`
`
let str: string = "Hello, World";
let num: number = 5;
let bol: boolean = true;
`
### `any`
`
let obj: any = { x: 0 };
obj.foo();
obj();
obj.bar = 100;
obj = "hello";

const n:number = obj;
`
### `function`

- Parameter type annotations
`
function greet (name: string) {
  console.log("Hello, " + name.toUpperCase());
}
great (42); // Error: Argument of type 'number' is not assignable to parameter of type 'string'.
`
- return type annotations
`
function getFavoriteNumber(): number {
  return 26;
}
`

- Anonymous Functions

const names = ["Alice", "Bob", "Eve"];
`
name.forEach(function (s) {
  console.log(s.toUppercase()); // Error: Property 'toUppercase' does not exist on type 'string'. Did you mean 'toUpperCase'?
})
`
`
name.forEach((s) => {
  console.log(s.toUppercase()); // Error: Property 'toUppercase' does not exist on type 'string'. Did you mean 'toUpperCase'?
})
`

### `Object Type`
`
function printCoord(pt: { x: number; y: number }) {
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}
printCoord({ x: 3, y: 7 });
`

- Optional Properties
`
function printName(obj: { first: string; last?: string }) {
  // ...
}
// Both OK
printName({ first: "Bob" });
printName({ first: "Alice", last: "Alisson" });
`

`
function printName(obj: { first: string; last?: string }) {
  // Error - might crash if 'obj.last' wasn't provided!
  console.log(obj.last.toUpperCase());
Object is possibly 'undefined'.
  if (obj.last !== undefined) {
    // OK
    console.log(obj.last.toUpperCase());
  }
 
  // A safe alternative using modern JavaScript syntax:
  console.log(obj.last?.toUpperCase());
}
`


























