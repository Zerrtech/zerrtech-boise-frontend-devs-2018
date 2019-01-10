# zerrtech-boise-frontend-devs-2018

## Technology Trends

JavaScript is at the top of several lists of the most popular technologies.  No surprise there.  Owns the front end, big presence on the backend, too.

Stack Overflow 2018 Developer Survey, for programming languages, JS on top for the 6th straight year

![Stack Overflow 2018 Languages](images/stack-overflow-2018-languages.png)

Source: [Stack Overflow 2018 Developer Survey - Languages](https://insights.stackoverflow.com/survey/2018/#technology-programming-scripting-and-markup-languages)

Octoverse says roughly the same thing

![Octoverse Languages](images/octoverse-languages.png)

Source: [Octoverse - Top Languages](https://octoverse.github.com/projects#languages)

Frameworks, Libraries, and Tools, Angular topping React

![Stack Overflow 2018 Frameworks](images/stack-overflow-2018-frameworks.png)

Source: [Stack Overflow 2018 Developer Survey - Frameworks](https://insights.stackoverflow.com/survey/2018/#technology-frameworks-libraries-and-tools)

State of JS approaches their survey in a little different way, React has a big edge on the "Used it, would use again"

![State of JS 2018 frontend frameworks](images/state-of-js-2018-frontend-frameworks.png)

Source: [State of JS 2018 - Front-end Frameworks](https://2018.stateofjs.com/front-end-frameworks/overview/)

State of JS 2018 Individual framework pages:
* [React](https://2018.stateofjs.com/front-end-frameworks/react/)
* [Vue.js](https://2018.stateofjs.com/front-end-frameworks/vuejs/)
* [Angular](https://2018.stateofjs.com/front-end-frameworks/angular/)

Most Loved Frameworks - React love

![Stack Overflow 2018 most loved frameworks](images/stack-overflow-2018-most-loved-frameworks.png)

Most Dreaded Frameworks - Angular creeping up towards the top

![Stack Overflow 2018 most dreaded frameworks](images/stack-overflow-2018-most-dreaded-frameworks.png)

Source: [Stack Overflow 2018 Developer Survey - Most Loved, Dreaded Frameworks](https://insights.stackoverflow.com/survey/2018/#technology-most-loved-dreaded-and-wanted-frameworks-libraries-and-tools)

VS Code somehow the most popular editor now

![Stack Overflow 2018 editor](images/stack-overflow-2018-editor.png)

Source: [Stack Overflow 2018 Developer Survey - Most Popular Dev Environments](https://insights.stackoverflow.com/survey/2018/#technology-most-loved-dreaded-and-wanted-frameworks-libraries-and-tools)


## Redux

![Redux logo](images/redux-logo-title-dark.png)

Only one major release this year, version 4 in April.  I'll highlight 3 things, although there are a [lot more](https://medium.com/@vyakymenko/whats-new-in-redux-4-major-breaking-changes-4f22a25da921)
* Updated TypeScript bindings
* Dropped support for IE < 11
* Dropped lodash dependency, so Redux became smaller by about 15% minified


## Typescript

![Typescript logo](images/typescript-logo.svg)

Lots of changes in TypeScript this year.  The year started with 2.7, including TypeScript 3 being released on July 30.  Mainly just want to cover the significant changes in Typescript 3+.  You can follow these yourself on the [What's new in TypeScript page](https://github.com/Microsoft/TypeScript/wiki/What's-new-in-TypeScript)

### Added a new "unknown" type, treated like a type-safe "any".

```javascript
// Only equality operators are allowed with unknown

function f10(x: unknown) {
    x == 5;
    x !== 10;
    x >= 0;  // Error
    x + 1;  // Error
    x * 2;  // Error
    -x;  // Error
    +x;  // Error
}

// No property accesses, element accesses, or function calls

function f11(x: unknown) {
    x.foo;  // Error
    x[5];  // Error
    x();  // Error
    new x();  // Error
}
```

[Source](https://github.com/Microsoft/TypeScript/wiki/What's-new-in-TypeScript#new-unknown-top-type)

### Support for defaultProps in JSX

TypeScript 2.9 and earlier didn’t leverage React defaultProps declarations inside JSX components. Users would often have to declare properties optional and use non-null assertions inside of render, or they'd use type-assertions to fix up the type of the component before exporting it.

```javascript
export interface Props {
    name: string;
}

export class Greet extends React.Component<Props> {
    render() {
        const { name } = this.props;
        return <div>Hello ${name.toUpperCase()}!</div>;
    }
    static defaultProps = { name: "world"};
}

// Type-checks! No type assertions needed!
let el = <Greet />
```

[Source](https://github.com/Microsoft/TypeScript/wiki/What's-new-in-TypeScript#support-for-defaultprops-in-jsx)

### Version selection now possible

Allows package maintainers to support updated typescript types.

```javascript
{
  "name": "package-name",
  "version": "1.0",
  "types": "./index.d.ts",
  "typesVersions": {
    ">=3.1": { "*": ["ts3.1/*"] }
  }
}
```

This package.json tells TypeScript to check whether the current version of TypeScript is running. If it's 3.1 or later, it figures out the path you've imported relative to the package, and reads from the package's ts3.1 folder. That's what that { "*": ["ts3.1/*"] } means - if you're familiar with path mapping today, it works exactly like that.

[Source](https://github.com/Microsoft/TypeScript/wiki/What's-new-in-TypeScript#version-selection-with-typesversions)

### Performance improvements

On a project we were working on this year, we were running into some big compile performance issues related to using React Material UI and interaction with TypeScript.  There were some changes to TypeScript that came out of this that improved performance.  Here is the [Issue](https://github.com/Microsoft/TypeScript/issues/25085) that explains it the best.
