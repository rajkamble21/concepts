## JS Library vs Framework


| **Criteria**               | **JavaScript Library**                                      | **JavaScript Framework**                                     |
|----------------------------|-------------------------------------------------------------|--------------------------------------------------------------|
| **Definition**             | A collection of pre-written code snippets and functions that can be called to perform specific tasks. | A complete architecture that provides a structure and guidelines for building applications. |
| **Control Flow**           | The developer has control over the flow of the application. They decide when and how to use the library. | The framework often controls the flow. Developers insert their code into the framework structure. |
| **Flexibility**            | More flexible; allows you to pick and choose functions as needed. | Less flexible; you must follow the framework’s structure and conventions. |
| **Size and Scope**         | Smaller in size and scope, designed to do specific things. Examples: jQuery, Lodash. | Larger in scope, providing a full toolkit for building an application. Examples: Angular, React, Vue.js. |
| **Learning Curve**         | Generally easier to learn due to its focused nature. | Can have a steeper learning curve as it often requires understanding the whole framework. |
| **Usage**                  | Used for adding specific functionality to an existing application. | Used for building the entire architecture of the application. |
| **Dependence on Other Tools** | Can be used independently or with other libraries. | Often relies on or integrates with other tools and libraries for a full development environment. |
| **Updates and Maintenance**| Generally less frequent updates; easier to maintain and update. | More frequent updates; can require more effort to maintain and keep up with changes. |
| **Examples**               | jQuery, D3.js, Lodash, Moment.js | Angular, Vue.js, React (though React is sometimes considered a library, it’s often used as a framework). |
| **Community and Ecosystem**| Smaller community, fewer plugins, and extensions. | Larger community, extensive plugins, and extensions available. |
| **Use Case**               | Ideal for small projects or adding specific features. | Ideal for large-scale applications where a consistent structure is beneficial. |


## Client side frameworks

A client-side framework is a collection of tools and libraries that help developers build and manage the front-end of web applications. It handles user interface components, routing, and state management, running entirely in the browser.

## what is webpack

Webpack is a popular open-source JavaScript module bundler used in modern web development. It takes modules with dependencies (like JavaScript files, CSS, images, etc.) and bundles them into a single or multiple output files, often referred to as "bundles." These bundles can then be served to the browser.

## babel 

babel is used to convert javascript code in a such way that it is understood by all older browsers


## Client Side Rendering Vs Server Side Rendering.

Here's a simple comparison table between Client-Side Rendering (CSR) and Server-Side Rendering (SSR) that you can use for an interview:

| **Aspect**                | **Client-Side Rendering (CSR)**                           | **Server-Side Rendering (SSR)**                           |
|---------------------------|----------------------------------------------------------|-----------------------------------------------------------|
| **Where rendering occurs** | In the user's browser (client-side)                      | On the web server (server-side)                            |
| **Initial load time**      | Slower (browser must download and execute JavaScript)    | Faster (HTML is pre-rendered and sent from the server)     |
| **Interactivity**          | Faster after initial load (dynamic content loads quickly)| Slower as each interaction may require a server request    |
| **SEO**                    | Not ideal by default (search engines may not see content)| Better (content is available for search engines)           |
| **User experience**        | Feels faster after the first load (SPA-like experience)  | Feels slower due to full-page reloads                      |
| **Complexity**             | Easier to implement for single-page applications         | More complex due to server-side logic and routing          |
| **Network requests**       | Fewer requests after initial load (loads all at once)    | More frequent as each page interaction may require a request |
| **Caching**                | Harder to cache dynamic content                          | Easier to cache static content                            |
| **Examples**               | React, Angular, Vue.js (when using CSR)                  | Traditional websites, Next.js, Nuxt.js (when using SSR)   |

## Why are we using vite.js to create React application instead of create-react-app.

### **1. Faster Development:**
### **2. Modern Features:**
### **3. Smaller Build Size:**
### **4. Easier Configuration:**
### **5. Growing Popularity:**

## What is the role of Babel in React?

babel is used to convert modern javascript features to older one, because some older browser does not support modern jaavscript features. In case of react it is used to convert JSX & ES6 into browser understandable javascript.

## What is bundler and understand how webpack works.

### What is a Bundler?

A **bundler** is a tool that takes all the different files in your project (like JavaScript, CSS, images, etc.) and combines them into a single or few files that can be efficiently loaded by a browser. This process is essential for optimizing web applications, making them faster and more efficient by reducing the number of requests the browser needs to make.

### How Webpack Works

**Webpack** is one of the most popular bundlers, and here's a simple overview of how it works:

works only with JS and JSON

1. **Entry Point**: Webpack starts with an entry point, typically a single file like `index.js`. This is where it begins analyzing your code to figure out what other files are needed.

2. **Dependency Graph**: Webpack builds a dependency graph by following `import` or `require` statements in your code. It keeps track of how all the modules and assets are connected.

3. **Loaders**: As Webpack processes files, it uses loaders to transform them. For example, it can use a Babel loader to convert JSX or ES6+ code into plain JavaScript that browsers can understand.

4. **Plugins**: Webpack also uses plugins to perform additional tasks, like optimizing your files, injecting environment variables, or minifying your code to reduce file size.

5. **Output**: After bundling everything together, Webpack outputs the final files (usually JavaScript bundles, but also CSS or other assets) that your browser will load.

**In short**: Webpack organizes, transforms, and optimizes your project's files, bundling them into a few efficient files that are ready for the browser to use.


## What is JSX

JSX in react stands for Javascript XML wich is used to create reusable react components. it is a syntactic sugar for the React.createElement( ) function. It allows us to code faster by writing HTML like ocde inside javascript.

## What is component in React?

component in react is a reusable building block of UI. we can construct components using classess or functions.Componets can have props which is used to transferdata from parent component to child component, it can have states which are used to store infomation like variables. Each components can have lifecycle method like componentdidmount, componentdidupdate & componentwillunmount. It has its's own logic and appearance or logic. A component can be as small as button or as lasrg as full page.

## Different types of components uses in React

| **Functional Components** | **Class Components** |
|---------------------------|----------------------|
| A functional component is just a plain JavaScript pure function that accepts props as an argument and returns a React element (JSX). | A class component requires you to extend from `React.Component` and create a `render` function that returns a React element. |
| There is no `render` method used in functional components. | It must have the `render()` method returning JSX (which is syntactically similar to HTML). |
| Functional components run from top to bottom and once the function is returned it can’t be kept alive. | The class component is instantiated, and different lifecycle methods are kept alive and are run and invoked depending on the phase of the class component. |
| Also known as Stateless components as they simply accept data and display them in some form. They are mainly responsible for rendering UI. | Also known as Stateful components because they implement logic and state. |
| React lifecycle methods (for example, `componentDidMount`) cannot be used in functional components. | React lifecycle methods can be used inside class components (for example, `componentDidMount`). |
| Hooks can be easily used in functional components to make them stateful. | It requires different syntax inside a class component to implement state. |
| Example: `const [name, setName] = React.useState(' ')` | Example: `constructor(props) { super(props); this.state = { name: ' ' } }` |
| Constructors are not used. | Constructor is used as it needs to store state. |

## How component gets render in React?

1. first JSX is not a valid Javascript so babbel converts JSX into React.createElement()
2. React.CreateElement() creates an react element wich is a plain javascript object describing actual DOM in memory
3. now the react component is rendered to the actual dom using ReactDOM.render() method, it takes an react element and mounts to the specific node.
4. if there is any change in state then the current updated reactDOM is compared with previous dom and only differences are updatded instaed of updating entire DOM, this way it is efficint and fast

## difference between Props and state

| **Props** | **State** |
|-----------|-----------|
| The Data is passed from one component to another. | The Data is passed within the component only. |
| It is Immutable (cannot be modified). | It is Mutable (can be modified). |
| Props are read-only. | The state is both read and write. |
| Props do not have default values unless specified. | State can have default values set in the component's constructor. |
|Does not trigger lifecycle methods directly. |	Can trigger lifecycle methods when state changes.|
| Props are used for communication between components. | State is used for rendering dynamic changes within the component. |

## What are hooks.

hooks are used to declare states and use react lifecycle methods in functional components.

## what is useState

useState is a built-in react hook which is used to declare state in functional component. we import useState from react and pass initial value as parameter to useState, in return it provides array of two values first is variable second is setter function. variable is used to access current value of that state while setter function is used to update that state.

## what is useEffect 

useEffect is used to deal with side effects in react in functional components. we pass dependancy array to the useEffect based on which useEffect changes it's behaviour,

suppose we passed empty dependancy array then useEffect will be invoked only one time after the component mounts to the ReactDOO,
If we passed dependancy array with state variables then useEffect will be invoked when the state variables changes
If we do not passed dependancy array then the useEffect will be invoked after the component undergo rerendering or after the component Mounts to the ReavctDOM.

## what is useRef

it is used to create varibles which does not caouse re- render whenever we update them

## what is lifting state up

This is called “lifting state up”. By moving state up, you’ve shared it between components.

