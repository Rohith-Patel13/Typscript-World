```ts
/**
 * Typescript: The modern way to write Javascript
 * @see https://youtube.com/playlist?list=PL1BztTYDF-QNrddrcvejiw5vxSZSPIRfn&si=XzlfHk5QtV-BhDe-
 */
```

1. use Backticks(``) for multiple strings
2. 
```ts
   console.log(Boolean(null))
   console.log(Boolean(''))
   console.log(Boolean(undefined))
   console.log(Boolean(0))
   console.log(Boolean(' '))
```
3. 
```ts
  let person:object = {
   name: "John",
   age:31,gender
  };
  person = {name:"rohith"}
```
4. 
```ts
  let person:object = {
   name: "John",
   age:31,gender
  };
  console.log(person.name) // property `name` does not exist in `person` object
```
5. 
```ts
let test;
console.log(typeof test) // undefined
console.log(test) // undefined
```
6. 
```ts
// Literal Type in TypeScript
const str: "Hello" = "Hello";
console.log(str)
```
7. 
```ts
// Type Alias: Providing a custom name for your type
type StringOrNumber = string | number
```
8. 
```ts
// enums
```
9. 
```ts
// void return type in function: If a function not going to return any value i.e if that function simply doing some calculation, then in that case we can set that type as `void`

// In js or ts if a function not returning any value and if we try to log the returned value then that will be `undefined`
```
10. 
```ts
// Function as Type
let greet: Function; // any function can assignable to `greet` variable
greet = 100 // Type 'number' is not assignable to type 'Function'.
```
11. 
```ts
let greet: (num:string) => void
```
12. 
```ts
// Function Type for Callback
```
13. 
```ts
// `unknown` type
// The `unknown` type represents any value. This is similar to the `any` type, but is safer because it’s not legal to do anything with an unknown value
let inputVal:unknown
let uname:string
inputVal="100"
uname=inputVal // Type 'unknown' is not assignable to type 'string'.

let inputVal:unknown 
let uname:string
inputVal="100"
uname=inputVal as string // Error fixed
```
14. 
```ts
// `any` type
// any is the most permissive type in TypeScript. It essentially turns off type checking for the variable it is assigned to.
let inputVal:any
let uname:string
inputVal=100
uname=inputVal 
```
15. 
```ts
// `never` type: function is never going to return a value not even undefined
function createError():never{
  throw("page not found",404)
}
console.log(createError())

function infiniteLoop():never{
  while(true){

  }
}


function someFunc():void{
  return;
}
console.log(someFunc()) // [LOG]: undefined 
```

16. `target` in `tsconfig.json` file
17. `exclamation symbol in typescript` 
18. `lib` in `tsconfig.json` file and we use `identifiers` in it like `es2016`, `dom`
19. enabling `sourceMap` option in `tsconfig.json` file if you want to debug `typescript` code in browser's developer tool
20. `noEmit` option is used if you don't want to compile your `ts` to `js` and just want to check whether the `ts` is compiled without error or not
21. `noEmitOnError` if `ts` contains some errors then we don't want to compile `ts` to `js`
22.  
```ts
"noImplicitAny": true,  /* Enable error reporting for expressions and declarations with an implied 'any' type. */
```
23. Array Destructuring | TypeScript Advance ES6 Features
```ts
// array destructuring uses position of array element
// based on the position of element in the array it is getting assigned to the variable
/**
 * @see https://www.typescriptlang.org/docs/handbook/variable-declarations.html#destructuring
 * /
```
24. Spread Operator | TypeScript Advance ES6 Features
```ts
const users: string[] = ["john","mike","sike"]
const spreadUsers = {...users}
console.log(spreadUsers) // [LOG]: { "0": "john", "1": "mike", "2": "sike" } 
console.log(...users) // [LOG]: "john",  "mike",  "sike" 
console.log([...users]) // [LOG]: ["john", "mike", "sike"] 
```
25. Rest Pattern & Rest Parameter | TypeScript Advance ES6 Features
```ts
// packs a list of values in to a single array
const [a,b, ...rest] = [1,2,3,4,5]
console.log(rest) // [LOG]: [3, 4, 5] 

// packs a list of values in to a single object
const totalObj = {
    one:1,
    two:2,
    three:3,
    four:4,
    five:5
}
const {one,two,...restObj} = totalObj
console.log(restObj) // [LOG]: { "c": 3, "d": 4, "e": 5 } 

// Rest parameter
function addNumbers(...numbers: number[]){
  console.log(numbers)
}
addNumbers(1,2,3)
addNumbers(1,3)
addNumbers(1,2,3,4,5)
addNumbers(1)
```
26. The Nullish Coalescing Operator | TypeScript Advance ES6 Features
```ts

/**
 * Nullish Coalescing operator returns the 1st argument if it is not `null/undefined`, Otherwise
 * the second one
 * denoted by: `??`
 */
let valueOne = ""
let storageOne = valueOne || "DEFAULT"
console.log(storageOne) // [LOG]: "DEFAULT"

let valueTwo = ""
let storageTwo = valueTwo ?? "DEFAULT"
console.log(storageTwo) // [LOG]: "" 
```
27. Optional Chaining | TypeScript Advance ES6 Features
```ts
/**
 * The optional chaining checks if the value in the left hand side is
 * not null or undefined then only proceed with the evaluation of
 * further expression but if the value in the left hand side of
 * optional chaining is null or undefined it will stop there itself
 * it will not evaluate any further expression
 */

let products = [
    {
        name: "iPhone",
        details: {
            color: 'black',
            ram: 8
        }
    },
    {
        name:'T-shirt'
    }
]

for (let prod of products) {
    console.log(prod.name)
    console.log(prod.details?.color)
}
```
28. Specifying a type for a function
```ts
// Specifying a type for a `sum` function
const sum: (num1:number) => number = num1 => num1 + 1;
console.log(sum(1)); // [LOG]: 2 
```
29. Default Function Parameter | TypeScript Advance ES6 Features
```ts
/**
 * 1. Using default parameter you can set a default value
 * for a parameter it's not mandatory to pass a value
 * for that parameter while calling the function
 * and when you don't pass a value for that parameter
 * then that default parameter will use it's default value
 * 
 * 2. Default parameter should always be the last parameter in the
 * parameter list, you cannot make a default parameter by keeping it as
 * the first parameter in the parameter list
 * 
 * 3. There is no such restriction like you can only
 * use one default parameter, you can use multiple 
 * default parameters but they should all come at end after 
 * your regular parameters
 */
function printDetails(name:string, age: number, jobTitle:string="software developer", company: string = "worko") {
    console.log(
        `Hi, My name is ${name}.I'm ${age} years old. I'm a ${jobTitle} at ${company} company.`
    )
}

printDetails("rohith", 23) // [LOG]: "Hi, My name is rohith.I'm 23 years old. I'm a software developer at worko company."
```
30. An Overview of OOP
```ts
/**
 * OOPs:
 *    1. Representing a real world entities using an object is known as OOPs 
 *    2. `Object` is the data that we work with and `Class` is the creator
 *       using which we create this data
 */
```
31. Creating & Using a Class
```ts
/**
 * 1. while creating a class the name must starts with the `Uppercase` letter
 */
class User {
    name: string
    age: number
    gender: string

    // `constructor` is a special method which gets called whenever we try to instantiate a class 
    constructor(n:string,a:number,g:string){
        this.name = n,
        this.age = a,
        this.gender = g
    }
}

const userOneObj = new User("rohith",23,"male")
const userTwoObj = new User("jenny",23,"male")

console.log(userOneObj) // [LOG]: User: { "name": "rohith", "age": 23,"gender": "male" } 
console.log(userTwoObj) // [LOG]: User: { "name": "jenny", "age": 23, "gender": "male" } 
```
32. Methods of a Class
```ts

class User {
    name: string
    age: number
    gender: string

    // `constructor` is a special method which gets called whenever we try to instantiate a class 
    constructor(n:string,a:number,g:string){
        this.name = n,
        this.age = a,
        this.gender = g
    }

    greetUser() {
        const message: string = `Hi ${this.name}`
        console.log(message)
    }
}

const userOneObj = new User("rohith",23,"male")
// console.log(userOneObj) // [LOG]: User: { "name": "rohith", "age": 23,"gender": "male" } 
userOneObj.greetUser() // [LOG]: "Hi rohith" 

const userTwoObj = new User("jenny",23,"male")
// console.log(userTwoObj) // [LOG]: User: { "name": "jenny", "age": 23, "gender": "male" } 
```
33. Access Modifiers | TypeScript Classes
```ts
class Employee {
    empName:string
    private salary: number
    baseLocation:string
    isEligible:boolean
    private hikePercent: number

    constructor(name:string,sal:number,loc:string,isEligible:boolean,hikePercent:number) {
        this.empName = name
        this.salary = sal 
        this.baseLocation = loc
        this.isEligible = isEligible
        this.hikePercent = hikePercent
    }

    getSalary(){
        if(this.isEligible){
            return (this.salary + this.salary * this.hikePercent/100)
        }

        return this.salary
    }
}

const employee = new Employee("rohith",37500,"banglore",true,20)
// employee.hikePercent() // Errors in code: Property 'hikePercent' is private and only accessible within class 'Employee'.

console.log(employee.getSalary()) // [LOG]: 45000
```
34. Shorthand Property Initializer
```ts
class Employee {
    constructor(
        public empName:string, 
        private salary:number, 
        private baseLocation:string, 
        public isEligible:boolean, 
        public hikePercent:number
    ) {}

    getSalary(){
        if(this.isEligible){
            return (this.salary + this.salary * this.hikePercent/100)
        }

        return this.salary
    }
}

const employee = new Employee("rohith",37500,"banglore",true,20)
// employee.hikePercent() // Errors in code: Property 'hikePercent' is private and only accessible within class 'Employee'.

console.log(employee.getSalary()) // [LOG]: 45000
```
35. Readonly Property 
```ts
/**
 * @see https://youtu.be/UnZOmy1EAgA?si=MqjXoTi1BZhIYxTv
 */
class Employee {
    constructor(
        public empName:string, 
        private salary:number, 
        private baseLocation:string, 
        public isEligible:boolean, 
        public hikePercent:number,
        readonly empId: number
    ) {}

    getSalary(){
        if(this.isEligible){
            return (this.salary + this.salary * this.hikePercent/100)
        }

        return this.salary
    }
}

const employee = new Employee("rohith",37500,"banglore",true,20, 207)
// employee.hikePercent() // Errors in code: Property 'hikePercent' is private and only accessible within class 'Employee'.

// console.log(employee.getSalary()) // [LOG]: 45000

console.log(employee.empId) // [LOG]: 207
```
36. Understanding Inheritance
```ts
/**
 * @see https://youtu.be/iTnB1BZdO-4?si=NNk3oK0BXF9O-WV3
 */
class Person {
    constructor(
        public name:string,
        public age: number,
        public gender: string
    ){}

    getAge() {
        return this.age
    }
}

class Employee extends Person {
    constructor(
        public name: string,
        public age: number,
        public gender: string,
        public salary: number,
        public bonus: number
    ){
        super(name,age,gender)
    }

    getSalary() {
        return this.salary
    }
}

const employeeObj = new Employee("rohith",23,"male",10000,5000)
console.log(employeeObj.getAge()) // [LOG]: 23 
```