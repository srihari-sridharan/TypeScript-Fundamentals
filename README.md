# TypeScript Fundamentals

- [TypeScript](#typescript)
    - [Need for TypeScript!](#need-for-typescript)
        - [JavaScript vs. Maintainability!](#javascript-vs-maintainability)
        - [Maintainable Code!](#maintainable-code)
        - [Encapsulation in JavaScript](#encapsulation-in-javascript)
        - [JavaScript Dynamic Types](#javascript-dynamic-types)
        - [Alternatives for TS](#alternatives-for-ts)
    - [TypeScript Features](#typescript-features)
        - [What is TypeScript?](#what-is-typescript)
        - [TypeScript to JavaScript](#typescript-to-javascript)
    - [Syntax](#syntax)
    - [Keywords and Operators](#keywords-and-operators)
    - [Code Hierarchy](#code-hierarchy)
    - [Framework Options and Tools](#framework-options-and-tools)
    - [Basic Types](#basic-types)
        - [Boolean](#boolean)
        - [Number](#number)
        - [String](#string)
        - [Arrays](#arrays)
        - [Tuple](#tuple)
        - [Enum](#enum)
        - [Any](#any)
        - [Void](#void)
        - [Null and Undefined](#null-and-undefined)
        - [Never](#never)
        - [Type assertions](#type-assertions)
        - [A note about `let`](#a-note-about-let)
        - [Ambient Declarations](#ambient-declarations)
    - [Type Definition Files](#type-definition-files)
    - [Object Types](#object-types)
    - [Functions](#functions)
    - [Classes](#classes)
        - [Defining a Class](#defining-a-class)
        - [Complex Types](#complex-types)
        - [Instantiating a Type](#instantiating-a-type)
        - [Casting Types](#casting-types)
    - [Extending Types - Inheritance](#extending-types---inheritance)
    - [Interfaces](#interfaces)
        - [Optional Members](#optional-members)
        - [Implementing an Interface](#implementing-an-interface)
        - [Using interface as a Type](#using-interface-as-a-type)
    - [Extending an Interface](#extending-an-interface)
        - [Defining an Extended Interface](#defining-an-extended-interface)
        - [Using as Extended Interface](#using-as-extended-interface)
    - [TypeScript Modules and Namespaces](#typescript-modules-and-namespaces)
        - [Why Modules?](#why-modules)
        - [What is a Module?](#what-is-a-module)
        - [Export](#export)
            - [Export statements](#export-statements)
            - [Re-exports](#re-exports)
        - [Import](#import)
            - [Import a single export from a module](#import-a-single-export-from-a-module)
            - [Import the entire module into a single variable, and use it to access the module exports](#import-the-entire-module-into-a-single-variable-and-use-it-to-access-the-module-exports)
            - [Import a module for side-effects only](#import-a-module-for-side-effects-only)
    - [Namespaces](#namespaces)
        - [Alias Names](#alias-names)
    - [Further Reading](#further-reading)

## Need for TypeScript!

### JavaScript vs. Maintainability!

This has been a challenge with SPA. There are design patterns to solve this problem, that said, super set languages like TypeScript makes this easier and simpler.

### Maintainable Code!

Importance of source code maintainability!

### Encapsulation in JavaScript

* Function Spaghetti Code to Ravioli Code (JavaScript Patterns)

### JavaScript Dynamic Types

* JS provides dynamic type system
* The good:
    * Variables can hold any object (number, string, array, object, function, etc.)
    * Types determined on the fly
    * Implicit type coercion (ex: string to number)
* The bad:
    * Enterprise applications can have many 1000s of lines of code to maintain
    * Difficult to ensure proper types are passed without tests - more code required for validating and ensuring type safety
    * Not all developers use === for comparison

### Alternatives for TS

* DART - https://www.dartlang.org
* CoffeeScript - http://coffeescript.org/
* Pure JS and apply JS Patterns

## TypeScript Features

### What is TypeScript?

* https://www.typescriptlang.org/index.html defines it as - "Typescript is a superset of JavaScript that complies to plain JavaScript."
* Flexible Options
    * Any Browser
    * Any Host
    * Any OS
    * Open Source
    * Tool Support
* Key TypeScript Features
    * Supports standard JavaScript code
    * Provides static typing
    * Encapsulation through classes and modules
    * Support for constructors, properties and modules
    * Define interfaces
    * Lambdas for functions (Arrow syntax `() => {}`)
    * Intellisense and syntax checking

### TypeScript to JavaScript
```TS
// Source TypeScript
class Greeter {
    greeting: string;
    constructor(message: string) {
        this.greeting = message;
    }
    greet() {
        return "Hello, " + this.greeting;
    }
}

let greeter = new Greeter("world");

let button = document.createElement('button');
button.textContent = "Say Hello";
button.onclick = function() {
    alert(greeter.greet());
}

document.body.appendChild(button);
```

```JavaScript
// Generated JavaScript
var Greeter = /** @class */ (function () {
    function Greeter(message) {
        this.greeting = message;
    }
    Greeter.prototype.greet = function () {
        return "Hello, " + this.greeting;
    };
    return Greeter;
}());
var greeter = new Greeter("world");
var button = document.createElement('button');
button.textContent = "Say Hello";
button.onclick = function () {
    alert(greeter.greet());
};
document.body.appendChild(button);
```

## Syntax

* Being superset of JavaScript - follows the same syntax rules:
    * `;` ends an expression
    * {} brackets define the code blocks
* Most of JavaScript key words hold good.
* Remember: TS is super set of JS - meaning every valid JS code is a valid TS code.

## Keywords and Operators

* `class` - Container for members such as properties and functions
* `constructor` - Provides initialization functionality in a class
* `exports` - Export a member from a module
* `extends` - Extend a class or interface
* `implements` - Implement an interface
* `imports` - Import a module
* `interface` - Defines code contract that can be implemented by types
* `module/namespace` - Container for classes and other code
* `public/private` - Member visibility modifiers
* `...` - Rest parameter syntax
* `=>` - Arrow syntax used with definitions and functions
* `<type-name>` - < > characters use to cast/convert between types
* `:` - Separator between variable/parameter names and types

## Code Hierarchy

* Module/Namespaces
    * Classes (implement interfaces)
        * Fields
        * Constructor
        * Properties
        * Functions

## Framework Options and Tools

* Node.js
* TypeScript Playground
* Sublime
* Emacs
* Vi
* Visual Studio
* Visual Studio Code

## Basic Types

### Boolean

The most basic datatype is the simple true/false value, which JavaScript and TypeScript call a `boolean` value.

```TS
let isDone: boolean = false;
```

### Number

As in JavaScript, all numbers in TypeScript are floating point values. These floating point numbers get the type number. In addition to hexadecimal and decimal literals, TypeScript also supports binary and octal literals introduced in ECMAScript 2015.

```TS
let decimal: number = 64;
let hex: number = 0xf01d;
let binary: number = 0b1110;
let octal: number = 0o734;
```

### String

As in other languages, we use the type string to refer to these textual datatypes. Just like JavaScript, TypeScript also uses double quotes (") or single quotes (') to surround string data.

```TS
let color: string = "blue";
color = 'red';

// Template Strings
let fullName: string = `Srihari Sridharan`;
let age: number = 30;
let sentence: string = `Hello, my name is ${ fullName }.

I'll be ${ age + 1 } years old next year.`;
```

### Arrays

2 ways of declaring arrays!

```TS
// 1. Using []  syntax
let numbers: number[] = [1, 2, 3, 4 , 5];

// 2. Using Array<Type> syntax
let numbers: Array<number> = [1, 2, 3, 4 , 5];
```

### Tuple

Tuple types allow you to express an array where the type of a fixed number of elements is known, but need not be the same. For example, you may want to represent a value as a pair of a string and a number:

```TS
// Declare a tuple type
let x: [string, number];
// Initialize it
x = ["hello", 10]; // OK
// Initialize it incorrectly
x = [10, "hello"]; // Error
```

When accessing an element with a known index, the correct type is retrieved:

```TS
console.log(x[0].substr(1)); // OK
console.log(x[1].substr(1)); // Error, 'number' does not have 'substr'
```

When accessing an element outside the set of known indices, a union type is used instead:

```TS
x[3] = "world"; // OK, 'string' can be assigned to 'string | number'
console.log(x[5].toString()); // OK, 'string' and 'number' both have 'toString'
x[6] = true; // Error, 'boolean' isn't 'string | number'
```

### Enum

A helpful addition to the standard set of datatypes from JavaScript is the enum. As in languages like C#, an enum is a way of giving more friendly names to sets of numeric values.

```TS
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
```

By default, enums begin numbering their members starting at 0. You can change this by manually setting the value of one of its members. For example, we can start the previous example at 1 instead of 0:

```TS
enum Color {Red = 1, Green, Blue}
let c: Color = Color.Green;
```

Or, even manually set all the values in the enum:

```TS
enum Color {Red = 1, Green = 2, Blue = 4}
let c: Color = Color.Green;
```

A handy feature of enums is that you can also go from a numeric value to the name of that value in the enum. For example, if we had the value 2 but weren’t sure what that mapped to in the Color enum above, we could look up the corresponding name:

```TS
enum Color {Red = 1, Green, Blue}
let colorName: string = Color[2];
alert(colorName); // Displays 'Green' as it's value is 2 above
```

### Any

We may need to describe the type of variables that we do not know when we are writing an application. These values may come from dynamic content, e.g. from the user or a 3rd party library. In these cases, we want to opt-out of type-checking and let the values pass through compile-time checks. To do so, we label these with the any type:

```TS
let notSure: any = 4;
notSure = "maybe a string instead";
notSure = false; // okay, definitely a boolean
```

The `any` type is a powerful way to work with existing JavaScript, allowing you to gradually opt-in and opt-out of type-checking during compilation. You might expect Object to play a similar role, as it does in other languages. But variables of type Object only allow you to assign any value to them - you can’t call arbitrary methods on them, even ones that actually exist:

```TS
let notSure: any = 4;
notSure.ifItExists(); // okay, ifItExists might exist at runtime
notSure.toFixed(); // okay, toFixed exists (but the compiler doesn't check)

let prettySure: Object = 4;
prettySure.toFixed(); // Error: Property 'toFixed' doesn't exist on type 'Object'.
```

The any type is also handy if you know some part of the type, but perhaps not all of it. For example, you may have an array but the array has a mix of different types:

```TS
let list: any[] = [1, true, "free"];
list[1] = 100;
```

### Void

`void` is a little like the opposite of any: the absence of having any type at all. You may commonly see this as the return type of functions that do not return a value:

```TS
function warnUser(): void {
    alert("This is my warning message");
}
```

Declaring variables of type void is not useful because you can only assign undefined or null to them:

```TS
let unusable: void = undefined;
```

### Null and Undefined

In TypeScript, both `undefined` and `null` actually have their own types named `undefined` and `null` respectively. Much like `void`, they’re not extremely useful on their own:

```TS
// Not much else we can assign to these variables!
let u: undefined = undefined;
let n: null = null;
```

By default null and undefined are subtypes of all other types. That means you can assign null and undefined to something like number.


However, when using the --strictNullChecks flag, null and undefined are only assignable to void and their respective types. This helps avoid many common errors. In cases where you want to pass in either a string or null or undefined, you can use the union type string | null | undefined.

> As a note: we encourage the use of --strictNullChecks when possible, but for the purposes of this handbook, we will assume it is turned off.

### Never

The `never` type represents the type of values that never occur. For instance, `never` is the return type for a function expression or an arrow function expression that always throws an exception or one that never returns; Variables also acquire the type `never` when narrowed by any type guards that can never be true.

The `never` type is a subtype of, and assignable to, every type; however, no type is a subtype of, or assignable to, `never` (except never itself). Even any isn’t assignable to `never`.

Some examples of functions returning `never`:

```TS
// Function returning never must have unreachable end point
function error(message: string): never {
    throw new Error(message);
}

// Inferred return type is never
function fail() {
    return error("Something failed");
}

// Function returning never must have unreachable end point
function infiniteLoop(): never {
    while (true) {
    }
}
```

### Type assertions

Sometimes you’ll end up in a situation where you’ll know more about a value than TypeScript does. Usually this will happen when you know the type of some entity could be more specific than its current type.

_Type assertions_ are a way to tell the compiler “trust me, I know what I’m doing.” A type assertion is like a type cast in other languages, but performs no special checking or restructuring of data. It has no runtime impact, and is used purely by the compiler. TypeScript assumes that you, the programmer, have performed any special checks that you need.

Type assertions have two forms. One is the _“angle-bracket”_ syntax:
```TS
let someValue: any = "this is a string";

let strLength: number = (<string>someValue).length;
```

And the other is the _as_-syntax:

```TS
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;
```

The two samples are equivalent. Using one over the other is mostly a choice of preference; however, when using TypeScript with JSX, only as-style assertions are allowed.

### A note about `let`

You may have noticed that so far, we’ve been using the `let` keyword instead of JavaScript’s `var` keyword which you might be more familiar with. The `let` keyword is actually a newer JavaScript construct that TypeScript makes available. Many common problems in JavaScript are alleviated by using `let`, as it is block scoped, so you should use it instead of `var` whenever possible. `var` is function scoped!

### Ambient Declarations

Use `declare` keyword for ambient declarations.

```TS
// lib.d.ts is referenced by default and contains references for the DOM and JavaScript
declare var document;
document.title = "Hello";
```

Equivalent JavaScript code:
```JS
// Ambient Declarations do not appear anywhere in the JavaScript
document.title = "Hello";
```

## Type Definition Files
* As you work with the DOM or other libraries you need a Type Definition file (`*.d.ts` file)
* `lib.d.ts` file is built-in out of the box for the DOM and JavaScript
* Additional Type Definition files for 3rd party scripts can be found at:
    * https://github.com/borisyankov/DefinitelyTyped
    * http://definitelytyped.org/
* Use `// <reference />` as shown below.

```TS
/// <reference path="jquery.d.ts" />
declare var  $;

var data = "Hello Srihari";
$("div").text(data);
```

## Object Types

* Examples - functions, classes, modules, interfaces, and literal types.
* May encompass - 
    * Properties
        * public or private
        * required or optional
    * Call signatures
    * Construct signatures
    * Index Signatures

```TS
// Object literals
var square = { h: 10, w: 20 };
var points: Object = { x: 10, y: 20 };

// Functions
var multiply = function(x: number, y: number) {
    return x * y;
};

// Declared as type 'Function'!
var square : Function;
square = function(x: number) {
    return x * x;
};
```

## Functions

* Parameter types (required and optional)
* Arrow function expressions
    * Compact form of function expressions
    * Omit the function keyword
    * Have scope of “this”
* Void
    * Used as the return type for functions that return no value

```TS
// TypeScript Code
var areaOfRectangle = function(h: number, w: number) {
    return h * w;
};

// The above function can be simplified using arrow function as () => {};
var areaOfRectangle = (h: number, w: number) => h * w;
```

```JS
// Emits the JavaScript Code
var areaOfRectangle = function (h, w) { 
    return h *  w;
};
```

```TS
// void used as return type for functions that return no value
var greet: (msg: string) => void;
greet = (message) => console.log(message);
greet("Hello!");
```

> Note: the declaration for variable `greet`. This can be seen as a delegate definition as in `C#`. greet can point to any function that satisfies this signature. `(msg: string) => void;`

```JS
// Emits the JavaScript Code
var greet;
greet = function (message) { 
    return console.log(message); 
};
greet("Hello!");
```


## Classes

### Defining a Class

* Classes act as containers for different members
* Typical members of a class include:
    * Fields
    * Constructors
    * Properties
    * Functions

```TS
class Car{
    engine: string;

    constructor(engine: string) {
        this.engine = engine;
    }
}

// Can be simplified as
class Car{
    // Shorthand way to declare a field
    constructor (public engine:string) { }

    // Public Methods
    start() { 
        return "Started " + this.engine; 
    }

    stop() { 
        return "Stopped " + this.engine; 
    }
}
```
* Properties can be defined as shown below. Note: you might need a backing variable.

```TS
class Car {
    private _engine: string;

    constructor(engine: string) { 
        this._engine = engine; 
    }
    
    get engine(): string { 
        return this._engine; 
    }

    set engine(value: string) {
        if (value == undefined) throw 'Supply an Engine!';
        this._engine = value; 
    }
}
```

### Complex Types

* Complex / user defined types can be used for a variable.

```TS
class Engine {
    constructor(
        public horsePower: number,
        public engineType: string
    ) { }
}

class Car {
    private _engine: Engine;

    constructor(engine: Engine) {
        this._engine = engine;
    }
}
```

### Instantiating a Type

* Types are instantiated using the `new` keyword.

```TS
var engine = new Engine(300, 'V8');
var car = new Car(engine);
```

### Casting Types

```TS
// This fails as HTMLElement cannot be assigned to HTMLTableElement
var table: HTMLTableElement = document.createElement('table'); // Error
```

* Cast `HTMLElement` to `HTMLTableElement`
```TS
var table: HTMLTableElement = <HTMLTableElement>document.createElement('table');
```

## Extending Types - Inheritance

* Types can be extended using the TypeScript `extends` keyword
* Child class constructor must call base class (`super`) constructor

```TS
class ChildClass extends ParentClass {
    constructor() {
        super();
    }
}
```

```TS
// Example
class Auto { 
    engine: Engine;
    constructor(engine: Engine) {
        this.engine = engine;
    }
}

class Truck extends Auto {
    fourByFour: boolean;
    
    constructor(engine: Engine, fourByFour: boolean) {
        super(engine);
        this.fourByFour = fourByFour; 
    }
}
```

## Interfaces

* What is an interface?
    * An interface is a description of the actions that an object can do.
    * What rather than how?
    * eg: Plug point

* E.g. A factory requires that all engines being built have a standard "interface".

```TS
interface IEngine { 
    start(callback: (startStatus: boolean, engineType: string) => void) : void;
    stop(callback: (stopStatus: boolean, engineType: string) => void) : void;
}
```

* Breaking this definition down, `start()` and `stop()` take 1 parameter and return void.
    * The parameter is `callback` - a function.
    * `callback` in turn is a pointer to the function which takes 2 arguments and returns void.
        * `startStatus/stopStatus` of type `boolean`
        * `engineType` of type `string`


### Optional Members
```TS
interface IAutoOptions { 
    engine: IEngine;
    basePrice: number;
    state: string;
    // make, model, and year are optional. Indicated a by a '?' next to the member name.
    make?: string;
    model?: string;
    year?: number;
}

```

### Implementing an Interface

* Interfaces provide a way to enforce a `contract`

```TS
class Engine  implements IEngine {
    constructor(public horsePower: number, public engineType: string) { }

    start(callback: (startStatus: boolean, engineType: string) => void) {
        window.setTimeout(() => { 
            callback(true, this.engineType);
        }, 1000); 
    }
    
    stop(callback: (stopStatus: boolean, engineType: string) => void) { 
        window.setTimeout(() => { 
            callback(true, this.engineType); 
        }, 1000);
    }
}
```

### Using interface as a Type

* Interfaces help ensure that proper data is passed.

```TS
class Auto { 
    engine: IEngine; 
    basePrice: number;
    //More fields…
    
    constructor(data: IAutoOptions) {
        this.engine = data.engine;
        this.basePrice = data.basePrice; 
    }
}
```

## Extending an Interface

### Defining an Extended Interface

* Extend the definition of an existing interface.

```TS
interface IAutoOptions {
    engine: IEngine; 
    basePrice: number; 
    state: string; 
    make?: string; 
    model?: string;
    year?: number;
}

// Defines IAutoOptions members plus custom members
interface ITruckOptions extends IAutoOptions {
    bedLength?: string;
    fourByFour: boolean;
}
```

### Using as Extended Interface

* The class Truck takes `ITruckOptions` as input.

```TS
class Truck extends Auto {
    bedLength: string;
    fourByFour: boolean;

    constructor(data: ITruckOptions) {
        super(data);
        this.bedLength = data.bedLength;
        this.fourByFour = data.fourByFour;
    }
}
```

## TypeScript Modules and Namespaces

### Why Modules?

* Separation of concerns
* Testable
* Maintainable
* Reusable

### What is a Module?

> **A note about terminology**: It's important to note that in TypeScript 1.5, the nomenclature has changed. "Internal modules" are now "namespaces". "External modules" are now simply "modules", as to align with ECMAScript 2015's terminology, (namely that `module X {` is equivalent to the now-preferred `namespace X {`).

Modules are executed within their own scope, not in the global scope; this means that variables, functions, classes, etc. declared in a module are not visible outside the module unless they are explicitly exported using one of the `export` forms. Conversely, to consume a variable, function, class, interface, etc. exported from a different module, it has to be imported using one of the `import` forms.

Modules are declarative; the relationships between modules are specified in terms of imports and exports at the file level.

Modules import one another using a module loader. At runtime the module loader is responsible for locating and executing all dependencies of a module before executing it. Well-known modules loaders used in JavaScript are the **CommonJS module loader for Node.js** and **require.js for Web applications**.

In TypeScript, just as in ECMAScript 2015, any file containing a top-level import or export is considered a module.

### Export

* Any declaration (such as a variable, function, class, type alias, or interface) can be exported by adding the export keyword.

```TS
// Code in Validation.ts
export interface StringValidator {
    isAcceptable(s: string): boolean;
}

// Code in ZipCodeValidator.ts
export const numberRegexp = /^[0-9]+$/;

export class ZipCodeValidator implements StringValidator {
    isAcceptable(s: string) {
        return s.length === 5 && numberRegexp.test(s);
    }
}
```
#### Export statements

* Export statements are handy when exports need to be renamed for consumers.

```TS
class ZipCodeValidator implements StringValidator {
    isAcceptable(s: string) {
        return s.length === 5 && numberRegexp.test(s);
    }
}

export { ZipCodeValidator };
export { ZipCodeValidator as mainValidator };
```

#### Re-exports
*  A re-export does not import it locally, or introduce a local variable.

```TS
export class ParseIntBasedZipCodeValidator {
    isAcceptable(s: string) {
        return s.length === 5 && parseInt(s).toString() === s;
    }
}

// Export original validator but rename it
export {ZipCodeValidator as RegExpBasedZipCodeValidator} from "./ZipCodeValidator";
```

 * A module can wrap one or more modules and combine all their exports using export * from "module" syntax.

```TS
// Code in AllValidators.ts
export * from "./StringValidator"; // exports interface 'StringValidator'
export * from "./LettersOnlyValidator"; // exports class 'LettersOnlyValidator'
export * from "./ZipCodeValidator";  // exports class 'ZipCodeValidator'
```

### Import

* Importing is just about as easy as exporting from a module. Importing an exported declaration is done through using one of the `import` forms below:

#### Import a single export from a module

```TS
import { ZipCodeValidator } from "./ZipCodeValidator";
let myValidator = new ZipCodeValidator();

// imports can also be renamed
import { ZipCodeValidator as ZCV } from "./ZipCodeValidator";
let myValidator = new ZCV();
```

#### Import the entire module into a single variable, and use it to access the module exports

```TS
import * as validator from "./ZipCodeValidator";
let myValidator = new validator.ZipCodeValidator();
```

#### Import a module for side-effects only

* Though not recommended practice, some modules set up some global state that can be used by other modules. These modules may not have any exports, or the consumer is not interested in any of their exports. To import these modules, use:

```TS
import "./my-module.js";
```

## Namespaces

* Namespaces (previously internal modules) are used to organize code in TypeScript.
* Additionally, anywhere the `module` keyword was used when declaring an internal module, the `namespace` keyword can and should be used instead.

* What happens behind the scenes?

```TS
namespace App.Shapes {
    export class Rectangle {
        constructor(public height: number, public width: number) { }
    }
}
```

```JS
var App;
(function (App) {
    var Shapes;
    (function (Shapes) {
        var Rectangle = /** @class */ (function () {
            function Rectangle(height, width) {
                this.height = height;
                this.width = width;
            }
            return Rectangle;
        }());
        Shapes.Rectangle = Rectangle;
    })(Shapes = App.Shapes || (App.Shapes = {}));
})(App || (App = {}));
```

* Code in a single file.

```TS
// Code in validation.ts
namespace Validation {
    export interface StringValidator {
        isAcceptable(s: string): boolean;
    }

    const lettersRegexp = /^[A-Za-z]+$/;
    const numberRegexp = /^[0-9]+$/;

    export class LettersOnlyValidator implements StringValidator {
        isAcceptable(s: string) {
            return lettersRegexp.test(s);
        }
    }

    export class ZipCodeValidator implements StringValidator {
        isAcceptable(s: string) {
            return s.length === 5 && numberRegexp.test(s);
        }
    }
}
```

* Hard to maintain in a single file. Can be split across files.

```TS
// Code in Validation.ts
namespace Validation {
    export interface StringValidator {
        isAcceptable(s: string): boolean;
    }
}
```

```TS
// Code in LettersOnlyValidator.ts
/// <reference path="Validation.ts" />
namespace Validation {
    const lettersRegexp = /^[A-Za-z]+$/;
    export class LettersOnlyValidator implements StringValidator {
        isAcceptable(s: string) {
            return lettersRegexp.test(s);
        }
    }
}
```

```TS
// Code in ZipCodeValidator.ts
/// <reference path="Validation.ts" />
namespace Validation {
    const numberRegexp = /^[0-9]+$/;
    export class ZipCodeValidator implements StringValidator {
        isAcceptable(s: string) {
            return s.length === 5 && numberRegexp.test(s);
        }
    }
}
```

```TS
// Code in Test.ts
/// <reference path="Validation.ts" />
/// <reference path="LettersOnlyValidator.ts" />
/// <reference path="ZipCodeValidator.ts" />

// Some samples to try
let strings = ["Hello", "98052", "101"];

// Validators to use
let validators: { [s: string]: Validation.StringValidator; } = {};
validators["ZIP code"] = new Validation.ZipCodeValidator();
validators["Letters only"] = new Validation.LettersOnlyValidator();

// Show whether each string passed each validator
for (let s of strings) {
    for (let name in validators) {
        console.log(
            """ + s + "" " 
            + (validators[name].isAcceptable(s) ? " matches " : " does not match ") 
            + name
        );
    }
}
```

* Once there are multiple files involved, we’ll need to make sure all of the compiled code gets loaded. There are two ways of doing this.
    * Compilation into a single file
        * Concatenated output using the --outFile flag to compile all of the input files into a single JavaScript output file: `tsc --outFile sample.js Test.ts`. The compiler will automatically order the output file based on the reference tags present in the files.
        * The files can also be specific individually `tsc --outFile sample.js Validation.ts LettersOnlyValidator.ts ZipCodeValidator.ts Test.ts`
    * Per-file compilation (the default) along with `<script>` tag.
        ```HTML
        <script src="Validation.js" type="text/javascript" />
        <script src="LettersOnlyValidator.js" type="text/javascript" />
        <script src="ZipCodeValidator.js" type="text/javascript" />
        <script src="Test.js" type="text/javascript" />
        ```

### Alias Names

* Using alias names to shorten lengthy namespace parts:

```TS
namespace Shapes {
    export namespace Polygons {
        export class Triangle { }
        export class Square { }
    }
}

import polygons = Shapes.Polygons;
let sq = new polygons.Square(); // Same as 'new Shapes.Polygons.Square()'
```

## Further Reading
Please consider perusing the below topics from **'TypeScript Handbook'**
* [Basic Types](https://www.typescriptlang.org/docs/handbook/basic-types.html)
* [Variable Declarations](https://www.typescriptlang.org/docs/handbook/variable-declarations.html)
* [Interfaces](https://www.typescriptlang.org/docs/handbook/interfaces.html)
* [Classes](https://www.typescriptlang.org/docs/handbook/classes.html)
* [Functions](https://www.typescriptlang.org/docs/handbook/functions.html)
* [Generics](https://www.typescriptlang.org/docs/handbook/generics.html)
* [Enums](https://www.typescriptlang.org/docs/handbook/enums.html)
* [Type Inference](https://www.typescriptlang.org/docs/handbook/type-inference.html)
* [Type Compatibility](https://www.typescriptlang.org/docs/handbook/type-compatibility.html)
* [Advanced Types](https://www.typescriptlang.org/docs/handbook/advanced-types.html)
* [Symbols](https://www.typescriptlang.org/docs/handbook/symbols.html)
* [Iterators and Generators](https://www.typescriptlang.org/docs/handbook/iterators-and-generators.html)
* [Modules](https://www.typescriptlang.org/docs/handbook/modules.html)
* [Namespaces](https://www.typescriptlang.org/docs/handbook/namespaces.html)
* [Namespaces and Modules](https://www.typescriptlang.org/docs/handbook/namespaces-and-modules.html)
* [Module Resolution](https://www.typescriptlang.org/docs/handbook/module-resolution.html)
* [Declaration Merging](https://www.typescriptlang.org/docs/handbook/declaration-merging.html)
* [JSX](https://www.typescriptlang.org/docs/handbook/jsx.html)
* [Decorators](https://www.typescriptlang.org/docs/handbook/decorators.html)
* [Mixins](https://www.typescriptlang.org/docs/handbook/mixins.html)
* [Triple-Slash Directives](https://www.typescriptlang.org/docs/handbook/triple-slash-directives.html)
* [Type Checking JavaScript Files](https://www.typescriptlang.org/docs/handbook/type-checking-javascript-files.html)