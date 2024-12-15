---
title: Display JavaScript parameters & member lists with IntelliSense
description: Learn how Visual Studio delivers richer IntelliSense, support for modern JavaScript features, and improved productivity features.
ms.date: 02/21/2023
ms.topic: conceptual
ms.subservice: javascript-typescript
helpviewer_keywords:
- IntelliSense [JavaScript]
- <reference> JavaScript XML tag
- JavaScript Code Editor
- XML code comments, JavaScript IntelliSense
- reference JavaScript XML tag
- JavaScript, IntelliSense
- code comments, JavaScript IntelliSense
- JavaScript, reference groups
- JavaScript Editor
- reference directives [JavaScript]
- JavaScript, XML documentation comments
- reference groups [JavaScript]
- JavaScript, reference directives
- IntelliSense [JavaScript], about
- IntelliSense extensibility [JavaScript]
- XML documentation comments [JavaScript]
author: mikejo5000
ms.author: mikejo
manager: mijacobs
---
# JavaScript IntelliSense

Visual Studio provides a powerful JavaScript editing experience right out of the box. Powered by a TypeScript-based language service, Visual Studio delivers rich IntelliSense, support for modern JavaScript features, and productivity features such as Go to Definition, refactoring, and more.

For more information about the general IntelliSense functionality of Visual Studio, see [Using IntelliSense](../ide/using-intellisense.md).

JavaScript IntelliSense displays information on parameter and member lists. This information is provided by the TypeScript language service, which uses static analysis behind the scenes to better understand your code.

TypeScript uses several sources to build up this information:

- [IntelliSense based on type inference](#intellisense-based-on-type-inference)
- [IntelliSense based on JSDoc](#intellisense-based-on-jsdoc)
- [IntelliSense based on TypeScript declaration files](#intellisense-based-on-typescript-declaration-files)
- [Automatic acquisition of type definitions](#automatic-acquisition-of-type-definitions)

## IntelliSense based on type inference

In JavaScript, most of the time there is no explicit type information available. Luckily, it's usually fairly easy to figure out a type given the surrounding code context.
This process is called type inference.

For a variable or property, the type is typically the type of the value used to initialize it or the most recent value assignment.

```js
var nextItem = 10;
nextItem; // here we know nextItem is a number

nextItem = "box";
nextItem; // now we know nextItem is a string
```

For a function, the return type can be inferred from the return statements.

For function parameters, there is currently no inference, but there are ways to work around this using JSDoc or TypeScript *.d.ts* files (see later sections).

Additionally, there is special inference for the following:

- "ES3-style" classes, specified using a constructor function and assignments to the prototype property.
- CommonJS-style module patterns, specified as property assignments on the `exports` object, or assignments to the `module.exports` property.

```js
function Foo(param1) {
    this.prop = param1;
}
Foo.prototype.getIt = function () { return this.prop; };
// Foo will appear as a class, and instances will have a 'prop' property and a 'getIt' method.

exports.Foo = Foo;
// This file will appear as an external module with a 'Foo' export.
// Note that assigning a value to "module.exports" is also supported.
```

## IntelliSense based on JSDoc

Where type inference doesn't provide the desired type information (or to support documentation), type information may be provided explicitly via JSDoc annotations.  For example, to give a partially declared object a specific type, you can use the `@type` tag as shown below:

```js
/**
 * @type {{a: boolean, b: boolean, c: number}}
 */
var x = {a: true};
x.b = false;
x. // <- "x" is shown as having properties a, b, and c of the types specified
```

As mentioned, function parameters are never inferred. However, using the JSDoc `@param` tag you can add types to function parameters as well.

```js
/**
 * @param {string} param1 - The first argument to this function
 */
function Foo(param1) {
    this.prop = param1; // "param1" (and thus "this.prop") are now of type "string".
}
```

See the JsDoc information in [Type Checking JavaScript Files](https://www.typescriptlang.org/docs/handbook/type-checking-javascript-files.html#supported-jsdoc) for the JsDoc annotations currently supported.

## IntelliSense based on TypeScript declaration files

Because JavaScript and TypeScript are based on the same language service, they are able to interact in a rich way. For example, JavaScript IntelliSense can be provided for values declared in a *.d.ts* file (see [TypeScript documentation](https://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html)), and types such as interfaces and classes declared in TypeScript are available for use as types in JsDoc comments.

Below, we show a simple example of a TypeScript definition file providing such type information (via an interface) to a JavaScript file in the same project (using a `JsDoc` tag).

![TypeScript definition file](https://raw.githubusercontent.com/wiki/Microsoft/TypeScript/images/decl1.png)

## Automatic acquisition of type definitions

In the TypeScript world, most popular JavaScript libraries have their APIs described by *.d.ts* files, and the most common repository for such definitions is on [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped).

By default, the language service tries to detect which JavaScript libraries are in use, and then automatically download and reference the corresponding *.d.ts* file that describes the library in order to provide richer IntelliSense. The files are downloaded to a cache located under the user folder at *%LOCALAPPDATA%\Microsoft\TypeScript*.

> [!NOTE]
> This feature is **disabled** by default if you're using a *tsconfig.json* configuration file, but may be set to enabled as outlined further below.

Currently, auto-detection works for dependencies downloaded from npm (by reading the *package.json* file), Bower (by reading the *bower.json* file), and for loose files in your project that match a list of roughly the top 400 most popular JavaScript libraries. For example, if you have *jquery-1.10.min.js* in your project, the file *jquery.d.ts* will be fetched and loaded in order to provide a better editing experience. This *.d.ts* file will have no impact on your project.

## Related content

- [Using IntelliSense](../ide/using-intellisense.md)