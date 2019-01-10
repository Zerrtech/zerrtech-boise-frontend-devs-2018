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



## Framework Updates and New Features

### React

- React v16
  - v16.0
    - Return array of elements and strings from `render` method
    - Fragments
    ```js
    return (
      <>
        <Child0 />
        <Child1 />
        <Child2 />
      </>
    )
    // Or
    
    return (
      <React.Fragment>
        <Child0 />
        <Child1 />
        <Child2 />
      </React.Fragment>
    )
    ```
    
  - v16.3
    - Context API
      - Pass data to deeply nested components without passing props all the way down
      - Use cases:
        - Authenticated users
        - Themes
        - Preferred language
      
  - v16.6
    - Suspense for code splitting
    ```js
    // This component is loaded dynamically
    const OtherComponent = React.lazy(() => import('./OtherComponent'));

    function MyComponent() {
      return (
        <React.Suspense fallback={<Spinner />}>
          <div>
            <OtherComponent />
          </div>
        </React.Suspense>
      );
    }
    ```
  - Coming soon:
    - React Hooks (~Q1 2019)
    - Concurrent Mode (~Q2 2019)
    - Suspense for Data Fetching (~mid 2019)

### Vue

- [Vue surpassed React in Github stars](https://hasvuepassedreactyet.surge.sh/)
  - **Vue:** 124k
  - **React:** 119k
- Vue CLI 3.0 released in August ([release announcement](https://medium.com/the-vue-point/vue-cli-3-0-is-here-c42bebe28fbb]))
- Vue 3.0 announced
  - [Roadmap](https://github.com/vuejs/vue/projects/6)
  - Planned release: End of Q2 2019
  - Features
    - Compiler rewrite
    - Added TSX for improved Typescript support
    - Speed, size, and memory improvements
    - Experimental Hooks API
    - Easier debugging with improved warnings and easier to trace re-renders


### Angular

- Angular v6
  - New CLI commands
    - `ng update` - recommends dependency updates
    - `ng add` - adds new capabilites to you app like PWA or Angular Elements
  - Angular Elements
    - Register Angular components as [custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements)
  - A lot of new Angular Material components
- Angular v7
  - Still no [Ivy Compiler](https://blog.angularindepth.com/inside-ivy-exploring-the-new-angular-compiler-ebf85141cee1)
    - Smaller, simpler, and faster
    - Tree shaking
  - Mostly bugfixes
## Browser Updates and New Features


