# Typescript
## Introduction to Typescript
 
* TypeScript is an Open Source Object oriented programming language developed and maintained by Microsoft Corporation. 
* TypeScript is a strongly typed language and its first version was introduced in 2012.
* TypeScript is a syntactic superset of JavaScript which adds static typing.
* This basically means that TypeScript adds syntax on top of JavaScript, allowing developers to add types.
* As TypeScript code is converted to JavaScript code it makes it easier to integrate into JavaScript projects. It is designed mainly for large Scale projects.

## Why to use TypeScript?

* JavaScript is a loosely typed language. It can be difficult to understand what types of data are being passed around in JavaScript.
* In JavaScript, function parameters and variables don't have any information! So developers need to look at documentation, or guess based on the implementation.
* TypeScript allows specifying the types of data being passed around within the code, and has the ability to report errors when the types don't match.
* For example, TypeScript will report an error when passing a string into a function that expects a number. JavaScript will not.

## Installation & Setup

In order to Install the Typescript one must install node.js on his computer system

**Step 1**: Go to the start menu and click on the command prompt.

**Step 2**: To install typescript we have to use NPM, NPM is called a node package manager. As its name suggests, it is used to install NodeJS packages onto our system.

Run the following command in the same NodeJS command prompt to install the typescript:

<!-- style="color:yellow;" --> **npm install --global typescript**

![intsallation1](/images/installation1.png)

The above command will install the typescript onto our local system. To verify the installation, run the following command:

<!-- style="color:yellow;" -->tsc -v

Here tsc is a typescript compiler and the -v flag indicates that we are displaying the version of the typescript as shown in the image.

At this point, typescript is successfully installed onto your system.

**Step 3**: To install a specific version of a typescript, use the following command with ‘@’ followed by version.

<!-- style="color:yellow;" -->npm install --global typescript@4.x.x

Here, ‘x’ can be changed with the version that we want to install, as shown in the image below:

![installation2](/images/installation2.png)

**Step 4**: To uninstall typescript, use the same command that is used to install the typescript and replace the installation with uninstall.

<!-- style="color:yellow;" -->npm uninstall --global typescript

![installation3](/images/installation3.png)

## Simple Project

Now, let’s create a simple project through typescript:

**Step 1**: Create a folder onto your desktop and create a file named “example.ts”. You can write whatever name you want for this file and folder.

**Step 2**: Open up the NodeJS command prompt and navigate to the folder path that we created in step 1.

<!-- style="color:yellow;" -->cd “C:\Users\MicroApt\Desktop\helloworldex”

![installation4](/images/installation4.png)

**Step 3**: Run the Initialization command in that command prompt to create the necessary configuration file for our simple project.

<!-- style="color:yellow;" -->tsc - -init

![installation5](/images/installation5.png)

This tsc –init command will create a configuration file for the typescript compiler called tsconfig.json. 

This file contains all the configurations for the typescript compiler that we will be going to use while executing the program.

**Step 4**: Open up the example.ts that we created in the step1. 

Below is the hello world code in the typescript.

It will display the string in the console that will confirm the working of the typescript compiler.

Typescript **example.ts Code:**

```
let helloWorld: string;	
helloWorld ="Typescript is successfully installed";	
console.log(helloWorld);
```

The above code should be pasted and saved in the main.ts file before executing the typescript compiler.

**Step 5**: Run the typescript compiler with the file name as an argument to see results.

<!-- style="color:yellow;" -->tsc

This will create a compiled JS file from that typescript file. And now to run the JS file we will be using the NodeJS as below.

**node main.js**

**Output:**

![installation5](/images/installation6.png)

## TypeScript Types

TypeScript supports some simple types (primitives).

|Built-in Data Type	|keyword   |	Description |
|-------------------|-------   |----------------|
|Number           	|number	   |It is used to represent both Integer as well as Floating-Point numbers|
|Boolean	        |boolean   |	Represents true and false |
|String	            |string	   |It is used to represent a sequence of characters|
|Void	            |void	   |Generally used on function return-types |
|Null	            |null	   |It is used when an object does not have any value|
|Undefined	        |undefined |Denotes value given to uninitialized variable|
|Any	            |any	   |If variable is declared with any data-type then any type of value can be assigned to that variable|

**Examples:**

let a: null = null;

let b: number = 123;

let c: number = 123.456;

let d: string = ‘‘Kiran’’;

let e: undefined = undefined;

let f: boolean = true;

**NOTE**: In data types, any is a special data-type, also the super data-type of all data types. If a variable is declared with any data type then we can assign any type value to that variable.

**Examples:**

let a: any = null;

let b: any =123;

let c: any = 123.456;

let d: any = ‘‘Kiran’’;

let e: any = undefined;

let f: any = true;

## Type Assignment

When creating a variable, there are two main ways TypeScript assigns a type:

* Explicit

* Implicit

In both examples below firstName is of type string

**Explicit Type**

Explicit - writing out the type:

**Example:**

```
let firstName: string = "Kiran";
console.log(typeof firstName);
```

**Output:**

```
String
```

Explicit type assignment are easier to read and more intentional.

**Implicit Type**

Implicit - TypeScript will "guess" the type, based on the assigned value:

**Example:**

```
let firstName = "Kiran";
console.log(typeof firstName);
```

**Output:**

```
String
```

**Note:** Having TypeScript "guess" the type of a value is called infer.
Implicit assignment forces TypeScript to infer the value.

#### Error in Type Assignment

TypeScript will throw an error if data types do not match.

**Example:**

```
let firstName: string = "Kiran"; // type string
firstName = 18; // attempts to re-assign the value to a different type
console.log(firstName);
```

**Output:**

```
prog.ts(2,1): error TS2322: Type 'number' is not assignable to type 'string'.
```

Implicit type assignment would have made firstName less noticeable as a string, but both will throw an error:

**Example:**

```
let firstName = "Kiran"; // inferred to type string
firstName = 18; // attempts to re-assign the value to a different type
console.log(firstName);
```

**Output:**

```
prog.ts(2,1): error TS2322: Type 'number' is not assignable to type 'string'.
```

## Type any

TypeScript has special types that may not refer to any specific type of data.

any is a type that disables type checking and effectively allows all types to be used.

**Example without any:**

```
let u = true;
u = "string"; // Error: Type 'string' is not assignable to type 'boolean'.
u.runANonExistentMethod(); // Error: Property 'runANonExistentMethod' does not exist on type 'boolean'.
console.log(Math.round(u)); // Error: Argument of type 'boolean' is not assignable to parameter of type 'number'.

```

**Output:**

```
prog.ts(2,7): error TS2322: Type 'string' is not assignable to type 'boolean'.
prog.ts(3,9): error TS2339: Property 'runANonExistentMethod' does not exist on type 'boolean'.
prog.ts(4,18): error TS2345: Argument of type 'boolean' is not assignable to parameter of type 'number'.

```

***Example with any:**

```
let v: any = true;
v = "string"; 
// v.runANonExistentMethod(); 
// no type error in the editor, but will still throw an error if commented in
console.log(Math.round(v));
```

**Output:**

```
NaN
```
## Type Unknown

Unknown type is used to make our code type-safe. when we use the unknown type we have to write extra code but finally, our code will be type-safe. type safety is nothing but the prevention of type errors. unknown is a similar, but safer alternative to any.

**Example:**

```
let val: unknown;
console.log(val);
val = true;
console.log(val);
val = 7;
console.log(val);
val = "Kiran";
console.log(val);
val = [1, 2, 3, 4];
console.log(val);
val = { name: "Kiran" };
console.log(val);
val = Math.random();
console.log(val);
val = null;
console.log(val);
val = undefined;
console.log(val);

```

**Output:**

```
Undefined
true
7
Kiran
[ 1, 2, 3, 4 ]
{ name: 'Kiran' }
0.776446663785197
null
undefined

```

unknown is best used when you don't know the type of data being typed. To add a type later, you'll need to cast it.

Casting is when we use the "as" keyword to say property or variable is of the casted type.


## Type never

never effectively throws an error whenever it is defined.

**Example:**

```
let x: never = true;     //error
let x2: never = 1;         // error
let x3: never = "geek";     // error

```

**Output:**

```
prog.ts(1,5): error TS2322: Type 'boolean' is not assignable to type 'never'.
prog.ts(2,5): error TS2322: Type 'number' is not assignable to type 'never'.
prog.ts(3,5): error TS2322: Type 'string' is not assignable to type 'never'.

```
A function that returns “never” must never have an endpoint, an infinite loop is an example of such a situation where the program never stops executing.

**Example:**

```
function greet(): never {
while (true) {
	console.log("Hello");
}
}
greet();

```
As discussed never type must be used only when the functions return nothing or never stop executing, in the output hello repeats infinitely. 

**Output:**

```
Hello
Hello
…………
```
## Type undefined & null

undefined and null are types that refer to the JavaScript primitives undefined and null respectively.

**Example:**

```
let y: undefined = undefined;
console.log(typeof y);
let z: null = null;
console.log(typeof z);

```

**Output:**

```
Undefined
Object

```

## TypeScript Arrays

An array is a homogeneous collection of similar types of elements that have a contiguous memory location and which can store multiple values of different data types.

TypeScript has a specific syntax for typing arrays.

**Example:**

```
const names: string[] = [];
names.push("Dylan"); // no error
names.push(3); // Error: Argument of type 'number' is not assignable to parameter of type 'string'.
console.log(names);

```

**Output:**

```
prog.ts(3,15): error TS2345: Argument of type 'number' is not assignable to parameter of type 'string'.

```

#### Types of Array

There are two types of an array: 

1.Single-Dimensional Array 

2.Multi-Dimensional Array

**Single-Dimensional Array**

It is the simplest form of an array that contains only one row for storing data. It contains single set of the square bracket (“[]”).

```
Syntax:

let arr_name:datatype[]
```
**Example:**

```
let arr:number[];
arr = [1, 2, 3, 4]
console.log("Array[0]: " +arr[0]);
console.log("Array[1]: " +arr[1]);

```

**Output:**

```
Array[0]: 1
Array[1]: 2

```
**Multi-Dimensional Array**

The data is stored in rows and columns (also known as matrix form) in a Multi-dimensional array.
TypeScript Arrays 

```
Syntax:  
let arr_name:datatype[][] = [ [a1, a2, a3], [b1, b2, b3] ];
```

**Example:**

```
var mArray:number[][] = [[10, 20, 30], [50, 60, 70]] ;
console.log(mArray[0][0]);
console.log(mArray[0][1]);
console.log(mArray[0][2]);
console.log();

```
**Output:**

```
10
20
30
```
#### Readonly & Inference

**Readonly**

The readonly keyword can prevent arrays from being changed.

**Example:**

```
const names: readonly string[] = ["Dylan"];
names.push("Jack"); // Error: Property 'push' does not exist on type 'readonly string[]'.
// try removing the readonly modifier and see if it works?
console.log(names);

```
**Output:**

```
prog.ts(2,13): error TS2339: Property 'push' does not exist on type 'readonly string[]'.

```
** Type Inference**

TypeScript can infer the type of an array if it has values.

**Example:1**

```
const numbers = [1, 2, 3]; // inferred to type number[]
numbers.push(4); // no error
// comment line below out to see the successful assignment 
numbers.push("2"); // Error: Argument of type 'string' is not assignable to parameter of type 'number'.
console.log(numbers);

```
**0utput:**

```
prog.ts(4): error TS2345: Argument of type 'string' is not assignable to parameter of type 'number'.
```

**Example:2**

```
const numbers = [1, 2, 3];
let head: number = numbers[0]; // no error
console.log(head);

```
**Output:**

```
1
```

#### Array Object

We can create an Array by using or initializing the Array Object. The Array constructor is used to pass the following arguments to create an Array: 

* With the numeric value which represents the size of an array. 

* A list of comma separated values.

```
Syntax:
1. let array_name:data-type[] = new Array(value);

```
**Example:**

```
// Initializing an Array by using the Array object.
let arr:string[] = new Array("Kiran", "1947", "Java", "sharan");
for(var i = 0;i<arr.length;i++) {
console.log(arr[i]);
}

```

**Output:**

```
Kiran
1947
Java
sharan

```
#### Passing an Array to a Function 

We can pass an Array to a function by specifying the Array name without an index. 

**Example:**

```
let arr:string[] = new Array("Kiran", "1947", "Java", "Sharan");
// Passing an Array in a function
function display(arr_values:string[]) {
for(let i = 0;i<arr_values.length;i++) {
	console.log(arr[i]);
} }
// Calling an Array in a function
display(arr);
console.log(display(arr));

```
**Output:**

```
Kiran
1947
Java
Sharan

```

## TypeScript Tuples

A tuple is a typed array with a pre-defined length and types for each index.

They allow each element in the array to be a known type of value.

To define a tuple, specify the type of each element in the array:

**Example:**

```
// define our tuple
let ourTuple: [number, boolean, string];
// initialize correctly
ourTuple = [5, false, ‘Kiran’];
console.log(ourTuple);

```
**Output:**

```
[5,false,‘Kiran’]

```
**what happens if we try to set them in the wrong order:**

**Example:**

```
let ourTuple :[number,string];
ourTuple = [sharan,6];
console.log(ourTuple);

```
**Output:**

```
error TS2322: Type 'number' is not assignable to type 'string'.

error TS2322: Type 'string' is not assignable to type  'number'.

```

**Declaration and initialization of a tuple separately by initially declaring the tuple as an empty tuple in Typescript.**

**Example:**

let arrTuple = [];  

arrTuple[0] = 501   

arrTuple[1] = 506 

**Accessing tuple Elements** With the help of index basis we can read or access the fields of a tuples, which is the same as an array. An index starts from zero too. 

**Example:**

```
var employee: [number, string] = [1, "Sharan"];
employee[0]; // returns 1
employee[1]; / return Sharan
console.log(employee);

```
**Output:**

```
1 Sharan
```

**We can declare heterogeneous datatypes in tuples like: number and string simultaneously.**

**Example:**

```
let empTuple = ["Vivek Singh", 22, "Honesty",“Microsoft”];  
console.log("Name of the Employee is : "+empTuple [0]);  
console.log("Age of the Employee is : "+empTuple [1]);  
console.log(empTuple [0]+" is working in "+empTuple [2]); 

```
**Output:**

```
Name of the Employee is : Vivek Singh Age of the Employee is : 22 Vivek Singh is working in Microsoft.

```
#### Operations on Tuple

A tuple has two operations:

* Push()

* Pop()
 
**Push() To add an element to the tuple with push operation.Elements will be added to last.** 

**Example:**

```
let employee: [number, string] = [1, "Steve"];
employee.push(2, "Bill"); 
console.log(employee); 

```
**Output:**

```
[1, ‘Steve’, 2, ‘Bill’]

```

This type of declaration is allowed in tuples because we are adding number and string values to the tuple and they are valid for the employee tuple.

**Pop() To remove an element to the tuple with pop() operation.**

**Example:**

```
let employee:[number,string,string] = [1,"Steve","Smith"];
employee.pop();
console.log(employee);

```
**0utput:**

```
[1,Steve]
```

## TypeScript Objects

TypeScript has a specific syntax for typing objects.

**Example:**

```
const car: { type: string, model: string, year: number } = {
  type: "Toyota",
  model: "Innova",
  year: 2009
};
console.log(car);

```
**Output:**

```
{ type: 'Toyota', model: 'Corolla', year: 2009 }
```
**Type Inference**

TypeScript can infer the types of properties based on their values.

**Example:**

```
const car = {
  type: "Toyota",
};
car.type = "Ford"; // no error
car.type = 2; // Error: Type 'number' is not assignable to type 'string'.
console.log(car);

```

**Output:**

```
prog.ts(5,7): error TS2322: Type 'number' is not assignable to type 'string'.

```

#### Object Types

In JavaScript, the fundamental way that we group and pass around data is through objects. In TypeScript, we represent those through object types.

As we’ve seen, they can be anonymous:

function greet(person: { name: string; age: number })
{

return "Hello " + person.name;

}

or they can be named by using either an **interface**

interface Person {

  name: string;

  age: number;

}

function greet(person: Person) {

  return "Hello " + person.name;

}

or a **type alias.**

type Person = {

  name: string;

  age: number;

};

function greet(person: Person) {

  return "Hello " + person.name;

}

In all three examples above, we’ve written functions that take objects that contain the property name (which must be a string) and age (which must be a number).

**Optional Properties**

Optional properties are properties that don't have to be defined in the object definition.

**Example without an optional property**

```
const car: { type: string, mileage: number } = 
{ // Error: Property 'mileage' is missing in type '{ type: string; }' but required in type '{ type: string; mileage: number; }'.
  type: "Toyota",
};
car.mileage = 2000;

```

**Example with an optional property**

```
const car: { type: string, mileage?: number } = { // no error
  type: "Toyota"
};
car.mileage = 2000;

```

## TypeScript Functions

Writing a function in TypeScript is similar to writing them in JavaScript but with added parameters and return type. Note that any JavaScript function is a perfectly valid TypeScript function.

```
Syntax: Let’s see a basic TypeScript function syntax (with two arguments)

function functionName(arg1: <arg1Type>, 
        arg2: <arg2Type>): <returnType> {
    // Function body...
}

```
**Return type**

The type return can be used to indicate a function return value.


**Example:**

```
// TypeScript Code
// Following function returns the addition
// of it's two parameters
function addTwo(a: number, b: number): number {
	return a + b;
}
console.log(addTwo(7, 8)); // logs 15

```
**Output:**

```
15
```

If no return type is defined, TypeScript will attempt to infer it through the types of the variables or expressions returned.

**Void Return Type**

The type void can be used to indicate a function doesn't return any value.

**Example:**

```
function printHello(): void {

  console.log('Hello!');
}

```
**Output:**

```
Hello!
```

#### Function Parameters

**Parameters**

Function parameters are typed with a similar syntax as variable declarations.

**Example:**

```
function multiply(a: number, b: number) {
  return a * b;
}
console.log(multiply(2,5));

```
**Output:**

```
10
```

If no parameter type is defined, TypeScript will default to using any, unless additional type information is available.

**Optional Parameters**

By default TypeScript will assume all parameters are required, but they can be explicitly marked as optional.

**Example:**

```
// the `?` operator here marks parameter `c` as optional
function add(a: number, b: number, c?: number) {
  return a + b + (c || 0);
}
console.log(add(2,5));

```
**Output:**

```
7
```
**Default Parameters**

For parameters with default values, the default value goes after the type annotation:

**Example:**

```
function pow(value: number, exponent: number = 10) {
  return value ** exponent;
}
console.log(pow(10));

```
**Output:**

```
10000000000

```
TypeScript can also infer the type from the default value.

**Named Parameters**

Typing named parameters follows the same pattern as typing normal parameters.

**Example:**

```
function divide({ dividend, divisor }: { dividend: number, divisor: number }) {
  return dividend / divisor;
}
console.log(divide({dividend: 10, divisor: 2}));

```
**Output:**

```
5
```
**Rest Parameters**

Rest parameters can be typed like normal parameters, but the type must be an array as rest parameters are always arrays.

**Example:**

```
function add(a: number, b: number, ...rest: number[]) {
  return a + b + rest.reduce((p, c) => p + c, 0);
}
console.log(add(10,10,10,10,10));

```
**Output:**

```
50
```

**Type Alias in functions**

Function types can be specified separately from functions with type aliases.

**Example:**

```
type Negate = (value: number) => number;
// in this function, the parameter `value` automatically gets assigned the type `number` from the type `Negate`
const negateFunction: Negate = (value) => value * -1;
console.log(negateFunction(10));

```
**Output:**

```
-10
```

## TypeScript Casting

Casting is the process of overriding a type.

Type casting in Typescript

The following types are supported by Typescript:

1.The built-in type(basic examples- number, string, boolean, and special type examples- any, unknown)

2.The additional type(examples- collections like ‘enum’ and even user-defined types)

Syntax of Type casting in Typescript

There are two types of syntax for type casting.

* let A: number = (<string> B).length;

* let A: number = (B as string).length;

**Casting with as**

A straightforward way to cast a variable is using the as keyword, which will directly change the type of the given variable.

**Example:**

```
let x: unknown = 'hello';
console.log((x as string).length);

```
**Output:**

```
5
```

Casting doesn't actually change the type of the data within the variable, for example the following code will not work as expected since the variable x is still holds a number.

```
let x: unknown = 4;
console.log((x as string).length); // prints undefined since numbers don't have a length

```
TypeScript will still attempt to typecheck casts to prevent casts that don't seem correct, for example the following will throw a type error since TypeScript knows casting a string to a number doesn't makes sense without converting the data:

```
console.log((4 as string).length); // Error: Conversion of type 'number' to type 'string' may be a mistake because neither type sufficiently overlaps with the other. If this was intentional, convert the expression to 'unknown' first.

```

**Casting with <> operator**

Using <> works the same as casting with as.

**Example:**

```
let x: unknown = 'hello';
console.log((<string>x).length);

```
**Output:**

```
5
```
**Note**:This type of casting will not work with TSX, such as when working on React files.

**Force casting**

To override type errors that TypeScript may throw when casting, first cast to unknown, then to the target type.


**Example:**

```
let x = 'hello';
console.log(((x as unknown) as number).length); // x is not actually a number so this will return undefined

```

## TypeScript UnionTypes

Union types are used when a value can be more than a single type.

Such as when a property would be string or number.

**Union** | **(OR)**

Using the | we are saying our parameter is a string or number:

**Example:**

```
function printStatusCode(code: string | number) {
  console.log(`My status code is ${code}.`)
}
printStatusCode(404);
printStatusCode('404');

```
**Output:**

```
My status code is 404.
My status code is 404.

```
**Union Type Errors**

**Note:** you need to know what your type is when union types are being used to avoid type errors:

**Example:**

```
function printStatusCode(code: string | number) {
  console.log(`My status code is ${code.toUpperCase()}.`) // error: Property 'toUpperCase' does not exist ontype 'string | number'.
  Property 'toUpperCase' does not exist on type 'number'
}

```

**Output:**

```
prog.ts(2,51): error TS2339: Property 'toUpperCase' does not exist on type 'string | number'.
Property 'toUpperCase' does not exist on type 'number'.

```

In our example we are having an issue invoking toUpperCase() as its a string method and number doesn't have access to it.

## TypeScript enum

TypeScript enums allow us to define or declare a set of named constants i.e. a collection of related values which could either be in the form of a string or number or any other data type.

**Example:**

```
enum CarName {
	Honda,
	Toyota,
	Alto,
	Swift,
}
console.log(CarName);
console.log("Value of Alto is : "+ CarName.Alto);

```

**Output:**

```
{
  '0': 'Honda',
  '1': 'Toyota',
  '2': 'Alto',
  '3': 'Swift',
  Honda: 0,
  Toyota: 1,
  Alto: 2,
  Swift: 3
}
Value of Alto is : 2

```
In this example, we will initialize one value inside an enum, so other values would be incremented on their own.


**Example:**

```
enum CarName {
	Honda = 10,
	Toyota,
	Alto,
	Swift,
}
console.log(CarName);
console.log("Value of Alto is : "+ CarName.Alto);

```
**Output:**

```
{
  '10': 'Honda',
  '11': 'Toyota',
  '12': 'Alto',
  '13': 'Swift',
  Honda: 10,
  Toyota: 11,
  Alto: 12,
  Swift: 13
}
Value of Alto is : 12

```
**String Enums**

Enums can also contain strings. This is more common than numeric enums, because of their readability and intent.

**Example:**

```
enum CardinalDirections {
  North = 'North',
  East = "East",
  South = "South",
  West = "West"
};
// logs "North"
console.log(CardinalDirections.North);
// logs "West"
console.log(CardinalDirections.West);

```
**Output:**

```
North
West

```
## TypeScript Type Aliases

TypeScript allows types to be defined separately from the variables that use them.

Type Aliases allow defining types with a custom name (an Alias).

Type Aliases can be used for primitives like string or more complex types such as objects and arrays.

**Example:**

```
// A new type is created
type type_alias = number | string | boolean;
// Variable is declared of the new type created
let variable: type_alias;
variable = 1;
console.log(variable);
variable = "geeksforgeeks";
console.log(variable);
variable = true;
console.log(variable);

```
**Output:**

```
1
geeksforgeeks
true
Implementing type alias in a function.

```
**Example:**

```
// A new type is created
type anotherType = number | string;
let variable: string;
function displayId(id: anotherType) {
if (typeof id === typeof variable) {
	return "my id is : " + id;
}
return "my id is : " + `${id.toString()}`;
}
// Argument of type string is passed into the function
console.log(displayId("AF565"));
// Argument of type number is passed into the function
console.log(displayId(565));

```
**Output:**

```
my id is : AF565
my id is : 565

```
## TypeScript  Interfaces

Aliases and Interfaces allows types to be easily shared between different variables/objects.

Interfaces are similar to type aliases, except they only apply to object types.

**Example:**

```
interface Rectangle {
  height: number,
  width: number
}
const rectangle: Rectangle = {
  height: 20,
  width: 10
};
console.log(rectangle);

```
**Output:**

```
{ height: 20, width: 10 }
```

**Extending Interfaces**

Interfaces can extend each other's definition.

Extending an interface means you are creating a new interface with the same properties as the original, plus something new.

**Example:**

```
interface Rectangle {                                                                              
  height: number,                                                                               
  width: number                                                                                   
}                                                                                                  
interface ColoredRectangle extends Rectangle {                                                                                  
  color: string
}
const coloredRectangle: ColoredRectangle = {
  height: 20,
  width: 10,
  color: "red"
};
console.log(coloredRectangle);

```
**Output:**

```
{ height: 20, width: 10, color: 'red' }

```

**Read only properties:** This is security property of interface which makes interface non-changeable. We can make any property read-only with readonly before property.

```
interface For_class{
    readonly name: string;
    id: number;                          
}

```

Here since we mark readonly to name so after assigning the value to name we can’t change the value of it.

**Optional properties:** This property makes the interface more useful as what if we are not clear that we should add a property in the structure of any object. 

In that case, we can make that property optional so it is not just in structure. We can make optional with the ? symbol.

```
interface For_function {
    (key: string, value ?: string) : void ;
}

```

Here value property is optional so, when we create the function with this interface it may or may not contain the value parameter.

## TypeScript Classes

Creating classes

Use the class keyword to declare a class in TypeScript. The syntax for the same is given below −

```
Syntax
class class_name { 
   //class scope 
}

```

**Members: Visibility**

Class members also be given special modifiers which affect visibility.

There are three main visibility modifiers in TypeScript.

* public - (default) allows access to the class member from anywhere

* private - only allows access to the class member from within the class

* protected - allows access to the class member from itself and any classes that inherit it, which is covered in the inheritance section below

**Example:**

```
class Person {
  private name: string;
  public constructor(name: string) {
    this.name = name;
  }
  public getName(): string {
    return this.name;
  }
}
const person = new Person("Jane");
console.log(person.getName()); // person.name isn't accessible from outside the class since it's private

```

**Output:**

```
Jane

```
**Parameter Properties**

TypeScript provides a convenient way to define class members in the constructor, by adding a visibility modifiers to the parameter.

**Example:**

```
class Person {
  // name is a private member variable
  public constructor(private name: string) {}

  public getName(): string {
    return this.name;
  }
}

const person = new Person("Jane");
console.log(person.getName());

```
**Output:**

```
Jane

```
**Readonly**

Similar to arrays, the readonly keyword can prevent class members from being changed.

**Example:**

```
class Person {
  private readonly name: string;

  public constructor(name: string) {
    // name cannot be changed after this initial definition, which has to be either at it's declaration or in the constructor.
    this.name = name;
  }
  public getName(): string {
    return this.name;
  }
}
const person = new Person("Jane");
console.log(person.getName());

```
**Output:**

```
Jane

```

#### How to use getters/setters in TypeScript ?

**Getter Method:**

**Note:** For extracting the value of a variable, getter accessor property is the conventional method. It is denoted by get keyword, in an object literal. A getter can be public, protected, private.

**Example:**

```
class Student {
	private _name: string = "Aman Rathod";
	private _semester: number;
	private _course: string;
	// Getter method to return name of
	// Student class
	public get name() {
		return this._name;
	}
}
// Access any property of the Student class
let student = new Student();
// Getter call
let value = student.name;
console.log(value);

```
**Output:**

```
Aman Rathod

```

**Setter Method:** 

For updating the value of a variable the setter accessor property is the conventional method which is used. They are denoted by a set keyword in an object literal.

**Example:**

```
class Student {
	private _name: string = "Aman Rathod";
	private _semester: number;
	private _course: string;
	// Getter method to return name
	// of Student class
	public get name() {
		return this._name;
	}
	// Setter method to set the semester number
	public set semester(thesem: number) {
		this._semester = thesem;
	}
	// Setter method
	public set course(thecourse: string) {
		this._course = thecourse;
	}
}
// Access any property of the Student class
let student = new Student();
// Setter call
student.semester = 5;
student.course = "Web Development";

```
#### Inheritance in Class

**Inheritance: Implements**

Interfaces can be used to define the type a class must follow through the implements keyword.

**Example:**

```
interface Shape {
  getArea: () => number;
}
class Rectangle implements Shape {
  public constructor(protected readonly width: number, protected readonly height: number) {}
  public getArea(): number {
    return this.width * this.height;
  }
}
const myRect = new Rectangle(10,20);
console.log(myRect.getArea());

```
**Output:**

```
200
```

**Note:**A class can implement multiple interfaces by listing each one after implements, separated by a comma like so: class Rectangle implements Shape, Colored {

**Inheritance: Extends**

Classes can extend each other through the extends keyword. A class can only extends one other class.

**Example:**

```
interface Shape {
  getArea: () => number;
}
class Rectangle implements Shape {
  public constructor(protected readonly width: number, protected readonly height: number) {}
  public getArea(): number {
    return this.width * this.height;
  }
}
class Square extends Rectangle {
  public constructor(width: number) {
    super(width, width);
  }
  // getArea gets inherited from Rectangle
}
const mySq = new Square(20);
console.log(mySq.getArea());

```
**Output:**

```
400
```
**Override**


When a class extends another class, it can replace the members of the parent class with the same name.
Newer versions of TypeScript allow explicitly marking this with the override keyword.


**Example:**

```
interface Shape {
  getArea: () => number;
}

class Rectangle implements Shape {
  // using protected for these members allows access from classes that extend from this class, such as Square
  public constructor(protected readonly width: number, protected readonly height: number) {}
  public getArea(): number {
    return this.width * this.height;
  }
  public toString(): string {
    return `Rectangle[width=${this.width}, height=${this.height}]`;
  }
}
class Square extends Rectangle {
  public constructor(width: number) {
    super(width, width);
  }
  // this toString replaces the toString from Rectangle
  public override toString(): string {
    return `Square[width=${this.width}]`;
  }
}
const mySq = new Square(20);
console.log(mySq.toString());

```
**Output:**

```
Square[width=20]

```

**Note:** By default the override keyword is optional when overriding a method, and only helps to prevent accidentally overriding a method that does not exist. Use the setting noImplicitOverride to force it to be used when overriding.

#### Abstract Classes

Classes can be written in a way that allows them to be used as a base class for other classes without having to implement all the members.

This is done by using the abstract keyword. Members that are left unimplemented also use the abstract keyword.

**Example:**

```
abstract class Polygon {
  public abstract getArea(): number;
  public toString(): string {
    return `Polygon[area=${this.getArea()}]`;
  }
}
class Rectangle extends Polygon {
  public constructor(protected readonly width: number, protected readonly height: number) {
    super();
  }
  public getArea(): number {
    return this.width * this.height;
  }
}
const myRect = new Rectangle(10,20);
console.log(myRect.getArea());

```
**Output:**

```
200

```

**Note:** Abstract classes cannot be directly instantiated, as they do not have all their members implemented.

## Type Generics

Generics allow creating 'type variables' which can be used to create classes, functions & type aliases that don't need to explicitly define the types that they use.

Generics makes it easier to write reusable code.

**Example:**

```
// This function takes array of any type that
// you determine while calling the function
function getArray<Type>(array: Type[]) {
	// Do some operations
	return array;
}
// We call the function
const arrayOfStrings = getArray < string > ([
	"John", "Sam", "Arnold"])
Console.log(arrayOfStrings);

```

**Output:**

```
[ 'John', 'Sam', 'Arnold' ]

```

We can also add more than a generic type, will create a function that takes two arguments  with undefined types T & V and return their values.

**Example:**

```
// Here we can define two generics type
// with any name you choose
function getInfo<T,V>(name:T,id:V){
	return `My name is ${name} and my id is ${id}`;
}
console.log(getInfo("John",123));

```
**Output:**

```
“My name is John and my id is 123”

```

#### Classes in Generics

Generics can be used to create generalized classes, like Map.

**Example:**

```
class NamedValue<T> {
  private _value: T | undefined;

  constructor(private name: string) {}

  public setValue(value: T) {
    this._value = value;
  }
  public getValue(): T | undefined {
    return this._value;
  }
  public toString(): string {
    return `${this.name}: ${this._value}`;
  }
}
let value = new NamedValue<number>('myNumber');
value.setValue(10);
console.log(value.toString());

```
**Output:**

```
myNumber: 10

```
#### Type Aliases and Default Value

**Type Aliases**

Generics in type aliases allow creating types that are more reusable.

**Example:**

```
type Wrapped<T> = { value: T };

const wrappedValue: Wrapped<number> = { value: 10 };
console.log(wrappedValue);

```
**Output:**

```
{ value: 10 }

```

**Default Value**

Generics can be assigned default values which apply if no other value is specified or inferred.

**Example:**

```
class NamedValue<T = string> {
  private _value: T | undefined;

  constructor(private name: string) {}

  public setValue(value: T) {
    this._value = value;
  }

  public getValue(): T | undefined {
    return this._value;
  }

  public toString(): string {
    return `${this.name}: ${this._value}`;
  }
}

let value = new NamedValue('myNumber');
value.setValue('myValue');
console.log(value.toString()); // myNumber: myValue

```
**Output:**

```
myNumber:myValue

```

#### Type Constraints

Constraints can be added to generics to limit what's allowed. The constraints make it possible to rely on a more specific type when using the generic type.

we’ll create an interface that describes our constraint.

**Example:**

```
interface props {
	id: number
}
// This function returns array of objects
// that must have id property
function getInfo <T extends props>(data:T[]):T[]{
	return data;
}
console.log(getInfo([{id:123,name:"John"},
	{id:345,name:"debruyne"},
	{id:789,name:"sam"}]));

```

**Output:**

```
[
  { id: 123, name: 'John' },
  { id: 345, name: 'debruyne' },
  { id: 789, name: 'sam' }
]

```

## TypeScript Utility Types

TypeScript provides several utility types to facilitate common type transformations. These utilities are available globally.

**Partial<Type>**

Constructs a type with all properties of Type set to optional. This utility will return a type that represents all subsets of a given type.

**Example:**

```
interface Point {
  x: number;
  y: number;
}           
let pointPart: Partial<Point> = {}; // `Partial` allows x and y to be optional
pointPart.x = 10;
console.log(pointPart);

```
**Output:**

```
{ x: 10 }

```
**Required**

Required changes all the properties in an object to be required.

**Example:**

```
interface Car {
  make: string;
  model: string;
  mileage?: number;
}
let myCar: Required<Car> = {
  make: 'Ford',
  model: 'Focus',
  mileage: 12000 // `Required` forces mileage to be defined
};
console.log(myCar);
```

**Output:**

```
{ make: 'Ford', model: 'Focus', mileage: 12000 }

```
**Record**

Record is a shortcut to defining an object type with a specific key type and value type.

**Example:**

```
const nameAgeMap: Record<string, number> = {
  'Alice': 21,
  'Bob': 25
};
console.log(nameAgeMap);

```
**Output:**

```
{ Alice: 21, Bob: 25 }

```

**Omit**

Omit removes keys from an object type.

**Example:**

```
interface Person {
  name: string;
  age: number;
  location?: string;
}
const bob: Omit<Person, 'age' | 'location'> = {
  name: 'Bob'
  // `Omit` has removed age and location from the type and they can't be defined here
};
console.log(bob);

```
**Output:**

```
{ name: 'Bob' }

```
**Pick**

Pick removes all but the specified keys from an object type.

**Example:**

```
interface Person {
  name: string;
  age: number;
  location?: string;
}
const bob: Pick<Person, 'name'> = {
  name: 'Bob'
  // `Pick` has only kept name, so age and location were removed from the type and they can't be defined here
};

```
**Output:**

```
{ name: 'Bob' }

```

**Exclude**

Exclude removes types from a union.

**Example:**

```
type Primitive = string | number | boolean
const value: Exclude<Primitive, string> = true; 
// a string cannot be used here since Exclude removed it from the type.
// if number is entered the typeofvalue will be a number
console.log(typeof value);

```
**Output:**

```
Boolean

```

**ReturnType**

ReturnType extracts the return type of a function type.

**Example:**

```
type PointGenerator = () => { x: number; y: number; };
const point: ReturnType<PointGenerator> = {
  x: 10,
  y: 20
};
console.log(point);

```
**Output:**

```
{ x: 10, y: 20 }

```

**Parameters**

Parameters extracts the parameter types of a function type as an array.

**Example:**

```
type PointPrinter = (p: { x: number; y: number; }) => void;
const point: Parameters<PointPrinter>[0] = {
  x: 10,
  y: 20
};
console.log(point);

```

**Output:**

```
{ x: 10, y: 20 }

```

## TypeScript Keyof

keyof is a keyword in TypeScript which is used to extract the key type from an object type.

**keyof with explicit keys**

When used on an object type with explicit keys, keyof creates a union type with those keys.

**Example:**

```
interface Person {
  name: string;
  age: number;
}
// `keyof Person` here creates a union type of "name" and "age", other strings will not be allowed
function printPersonProperty(person: Person, property: keyof Person) {
  console.log(`Printing person property ${property}: "${person[property]}"`);
}
let person = {
  name: "Max",
  age: 27
};
printPersonProperty(person, "name"); // Printing person property name: "Max"s

```

**Output:**

```
Printing person property name: “max”

```

## TypeScript Narrowing

Type narrowing is the process of moving a type from a less precise type to a more precise type.

we are going to learn various ways you can narrow types.

**Let's start with a simple function:**

```
function friends(input: string | number) {
	// code here
}

```

The above function can either take a number or a string. Let's say we want to perform different actions based upon whether input is a number or a string. In this case, we will use Javascripts type guards to check if it's a string or number, as shown below:

```
function someFunc(input: string | number) {
  if(typeof input === "string") {
    // do something with the string
    console.log("input is a string");
  }
  if(typeof input === "number") {
    // do something with number
    console.log("input is a number");
  }
}

```

#### Type Guards

In the above example, we used Javascripts type guards to narrow the type of input to either number or string. 

Type guards are used to check if a variable is of a certain type, i.e. number, string, object, etc.

When a type guard is used, Typescript expects that variable to be of that type. It will automatically type check its usage based on that information.

Here is a list of Javascripts type guards available:

string
if(typeof param === "string") {
  // do something with string value
}
number
if(typeof param === "number") {
  // do something with number value
}
bigint
if(typeof param === "bigint") {
  // do something with bigint value
}
boolean
if(typeof param === "boolean") {
  // do something with boolean value
}
symbol
if(typeof param === "symbol") {
  // do something with symbol value
}
undefined
if(typeof param === "undefined") {
  // do something with undefined value
}
object
if(typeof param === "object") {
  // do something with object value
}
function
if(typeof param === "function") {
  // do something with the function
}

#### Truthiness Narrowing

In this type of narrowing, we check whether a variable is truthy before using it.

When a variable is truthy, typescript will automatically remove the possibility of that variable being falsy i.e. undefined or null, etc, within the conditional check.

Take for instance the following example, where a function someFunction below takes an input, whose type is either a string or undefined (i.e. optional).

```

function someFunction(x?: string) {
  if(x) {
    console.log(typeof x) // "string"
  }
}

```

By checking whether input is truthy, the type of x becomes a string otherwise it's undefined.

#### Equality Narrowing

If two variables are equal, then the types of both variables must be the same. 

If one variable is of an imprecise type (i.e. unknown, any etc.) and is equal to another variable of a precise type, then typescript will use that information to narrow the type of the first variable.


Take the following function, which takes two parameters: x and y, with x being either a string or a number and y being a number.

When the value of x is equal to the value of y, then the type of x is inferred to be a number and otherwise a string.

```
function someFunction(x: string | number, y: number) {
    if(x === y) {
        // narrowed to number
        console.log(typeof x) // number
    } else {
        // this is not narrowed
        console.log(typeof x) // number or string
    }
}

```

#### The in operator narrowing

JavaScript in operator returns true if a key is found within an object and we can use this information for the purpose of narrowing.

```
type Circle = {
    radius: number;
}
type Rectangle = {
    length: number;
    height: number;
}
function calculateSquare(shape: Circle | Rectangle) {
    if("radius" in shape) {
        return 3.147 * shape.radius * shape.radius;
    } else {
        return shape.height * shape.length;
    }
}

```

####  Instanceof Class Narrowing

We can use instanceof to narrow a variables Type by checking if a variable is an instance of class or not, as shown below:

```
function dateToString(value: string | Date) {
  if(value instanceof Date) {
    return value.toISOString();
  }
  return value;
}

```

## TypeScript Modules

In TypeScript, a module is a way to organize code into reusable and sharable components.

 A module can contain one or more classes, functions, variables, and interfaces that can be accessed from other modules or files using the import statement.

Modules in TypeScript are defined using the export and import keywords. When a variable, function, or class is marked as export, it becomes available for use in other modules.

For example consider this module as math:

**Example:**

```
export function add(a: number, b: number): number {
  return a + b;
}
export function subtract(a: number, b: number): number {
  return a - b;
}
export const pi = 3.14;

```

In this module, we have exported two functions add and subtract, as well as a constant pi. These can be imported into other modules using the import keyword:

```
import { add, subtract, pi } from "./math";
console.log(add(1, 2)); // 3
console.log(subtract(5, 3)); // 2
console.log(pi); // 3.14

```

The import statement allows us to import specific exports from the math module. We can also use the * syntax to import all exports from a module:

```
import * as math from "./math";
console.log(math.add(1, 2)); // 3
console.log(math.subtract(5, 3)); // 2
console.log(math.pi); // 3.14

```
In this case, we have imported all exports from the math module into an object named math, which we can then use to access the exported functions and constants.



































