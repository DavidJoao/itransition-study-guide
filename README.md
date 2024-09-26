# ITransition Study Guide

## Company Overview

iTransition is a software development company specializing in various IT services, including web development, custom software solutions, and IT consulting. As an Intern Front-End Developer, understanding the company's tech stack, working culture, and the typical expectations for software development roles is crucial.

### Differences between Var, Let and Const
---
Var: Function-scoped or global if declared outside function. Are reassignable and will initialize as undefined. If you reference them before initialization it will not return an error but undefined.

Let: Block-scoped (limited to the block is declared). Can be reassignable and this type of variable is not initialized until the declaration is encountered. Accessing it before declaration results in ReferenceError.

Const: Block-scoped and cannot be reassigned after its initial assignment. If the variable holds an object or an array it can be modified, also needs to be initialuzed until declaration.

### Difference between HTML, CSS and JavaScript
----
HTML (Hypertext Markup Language): It's the structure of a webpage. Think of it as the skeleton of a house. HTML defines the different parts of a webpage (like headings, paragraphs, images, etc.). It gives meaning to the content, but by itself, it's pretty plain and unstyled.

CSS (Cascading Style Sheets): It’s the design or style of a webpage. If HTML is the skeleton of a house, CSS is the paint, furniture, and decorations that make it look good. CSS controls things like colors, fonts, spacing, and layout, making the webpage visually appealing.

JavaScript: It’s the behavior or functionality of a webpage. If HTML is the skeleton and CSS is the style, JavaScript adds the interactive features, like doors that open, lights that turn on, or buttons that perform actions. It lets you make the webpage dynamic and respond to user interactions (e.g., clicking, scrolling, submitting forms).

In summary, HTML builds the structure, CSS makes it look good, and JavaScript makes it interactive.


### HTML Basic Boilerplate
---

    <html lang="en"> 
        <head>
        <meta charset="UTF-8">
        <meta name="viewport">
        <title>Document</title>
        </head>
        <body></body>
    </html>
---

### Datalist Tag
Datalist tag is used to provide an autocomplete feature for an input element with a list of predefined elements:

    <input list="books" id="book"></input>
    <datalist id="books">
        <option value="JavaScript"/>
        <option value="Python"/>
        <option value="C++"/>
    <datalist>

### What is the DOM?
The Document Object Model (DOM) is a programming interface for web documents. It represents the structure of a document as a tree of objects, allowing programs to manipulate the document’s structure, style, and content.

#### Key Points
- Tree Structure: The DOM represents the document as a tree of nodes, where each node corresponds to a part of the document (e.g., elements, attributes, text).
- Manipulation: You can use the DOM to create, delete, and modify elements and content in a web document.
- Language-Independent: The DOM can be used with any programming language, though it’s most commonly used with JavaScript in web development.
- Dynamic Interaction: It allows for dynamic changes to the document, enabling interactive web pages.

### How do you make an API call?
##### API GET EXAMPLE CALL
    const apiUrl = 'https://api.example.com/data';
    // Make a GET request
    fetch(apiUrl)
    .then(response => {
        if (!response.ok) {
        throw new Error('Network response was not ok');
        }
        return response.json(); // Convert response to JSON
    })
    .then(data => {
        console.log(data); // Handle the data from the API
    })
    .catch(error => {
        console.error('There was a problem with the fetch operation:', error);
    });
#### API POST EXAMPLE CALL
    const apiUrl = 'https://api.example.com/data';

    // Define the data to be sent in the request body
    const data = {
    username: 'exampleUser',
    email: 'user@example.com'
    };

    // Make a POST request
    fetch(apiUrl, {
    method: 'POST', // Specify the request method
    headers: {
        'Content-Type': 'application/json' // Set the content type to JSON
    },
    body: JSON.stringify(data) // Convert the data to a JSON string
    })
    .then(response => {
        if (!response.ok) {
        throw new Error('Network response was not ok');
        }
        return response.json(); // Convert the response to JSON
    })
    .then(data => {
        console.log('Success:', data); // Handle the response data
    })
    .catch(error => {
        console.error('There was a problem with the fetch operation:', error);
    });

#### What are headers?
HTTP headers are pieces of information sent along with an HTTP request or response. They provide essential metadata about the request or response, such as content type, caching directives, and authentication credentials. Headers are structured as key-value pairs, with each header field separated from its value by a colon.

Types of HTTP Headers
- Request Headers: Provide information about the client and the resource being requested.
    - Example: Authorization: Bearer <token>
- Response Headers: Provide information about the server and the resource being sent.
    - Example: Content-Type: application/json
- Representation Headers: Describe the body of the resource, such as its MIME type.
    - Example: Content-Encoding: gzip
- Payload Headers: Contain information about the payload data, like content length.
    - Example: Content-Length: 348

### What is SOLID?
---
SOLID is a set of five design principles in object-oriented programming that help developers create more understandable, flexible, and maintainable software. These principles promote clean, modular, and scalable code that is easier to test and extend.

Here's a breakdown of the SOLID principles:

1. S - Single Responsibility Principle (SRP) 

- Definition: A class should have only one reason to change, meaning it should only have one responsibility or job.
- Purpose: This makes classes more modular and easier to maintain because changes to one functionality won't affect others.
- Example: If you have a class that handles both user authentication and email sending, it's better to split them into two classes: one for authentication and another for sending emails.
2. O - Open/Closed Principle (OCP)

- Definition: A class should be open for extension but closed for modification.
- Purpose: You should be able to extend the behavior of a class without modifying its existing code. This prevents breaking existing functionality when adding new features.
- Example: Instead of modifying a class directly to add new behavior, you can create new classes or subclasses to extend its functionality.
3. L - Liskov Substitution Principle (LSP)

- Definition: Subtypes must be substitutable for their base types without altering the correctness of the program.
- Purpose: You should be able to replace an object of a parent class with an object of a subclass without affecting the program.
- Example: If you have a class Bird and a subclass Penguin, even though Penguin can't fly, substituting Penguin for Bird should not break the behavior of methods that expect a Bird object.
4. I - Interface Segregation Principle (ISP)

- Definition: A client should not be forced to implement interfaces it doesn’t use. Instead of having large, general-purpose interfaces, create smaller, more specific ones.
- Purpose: This prevents "fat" interfaces with unused methods and ensures that clients depend only on what they actually need.
- Example: Instead of one Worker interface with many unrelated methods (e.g., work(), eat(), sleep()), you could split it into smaller interfaces like Workable (with a work() method) and Eatable (with an eat() method).
5. D - Dependency Inversion Principle (DIP)

- Definition: High-level modules should not depend on low-level modules. Both should depend on abstractions (e.g., interfaces). Also, abstractions should not depend on details; details should depend on abstractions.
- Purpose: This principle encourages you to rely on abstractions (like interfaces) rather than concrete implementations, making the code more flexible and decoupled.
- Example: If a class OrderProcessor directly depends on PayPalPaymentService, it would be tightly coupled to that payment service. By introducing an abstraction (like a PaymentService interface), OrderProcessor can work with any payment service (PayPal, Stripe, etc.) that implements the PaymentService interface.

### ISP in SOLID Principles
---
he ISP in SOLID stands for the Interface Segregation Principle. It means that a class should not be forced to implement interfaces it does not use. Instead of having one large interface, it is better to split it into smaller, more specific ones. This way, classes only need to implement the methods that are relevant to them.

---

### What is ReactJS?
ReactJS is a JavaScript library developed by Facebook for building user interfaces for singlepage applications. Is component-based which allows developers to build encapsulated components that manage their own state and can be used to create complex interfaces.

- Virtual DOM: React uses a virtual DOM to improve performance. When the state of an object changes, React updates the virtual DOM first, then it compares the virtual DOM with a snapshot of the previous DOM state, and finally, it updates the real DOM with only the changes.
- JSX: React uses JSX, a syntax extension that allows HTML to be written within JavaScript code. This makes the code easier to understand and debug.
- Ecosystem: React has a rich ecosystem with many libraries and tools that complement it, such as Redux for state management and React Router for routing.

### Features of React

1.- It uses virtual DOM instead of RealDOM considering that RealDOM manipulations are expensive.
2.- Supports server-side rendering.
3.- Follows unidirectional data flow or data binding.
4.- Uses reusable/composable UI components to develop the view. 

### Difference between an Element and Component
An element is a plain object describing what you want to appear on the screen in terms of the DOM nodes or other components. Elemens can contain other elements in their props. Creating a React element is cheap because once one element is created it is never mutated.

Syntax of an Element: 

    const element = React.createElement(
        'div',
        { id: 'new-element' },
        'Login'
    )
And finally it renders to the DOM using ReactDOM.render()

Components can be declared in a class with a render() method or can be defined as a function, for example:

    const Button = ({ onLogin }) => 
        <div id="login-button" onClick={Login} >Login</div>

#### Function Component Example

    function Greeting({ message }) {
        return <h1>{`Hello ${message}`}</h1>
    }

#### Class Component Example

    class Greeting extends React.Component {
        render () {
            return <h1>`Hello ${this.props.message}`</h1>
        }
    }

#### useState, useEffect and useContext
- useState: Manages state in functional components to keep track of a value.
- useEffect: Performs an action when the component mounts.
- useContext: Shares data across components without passing props manually.

#### How do you know when a component is mounted and unmounted?

A component is mounted when it is first rendered and added to the DOM.

---
    import React, { useEffect } from 'react';

    const MyComponent = () => {
    useEffect(() => {
        console.log('Component mounted');
    }, []); // Empty array ensures this runs only once after the initial render

    return <div>My Component</div>;
    };

    export default MyComponent;
---

A component is unmounted when it is removed from the DOM.

How: Return a cleanup function from the useEffect hook.

---
    import React, { useEffect } from 'react';

    const MyComponent = () => {
    useEffect(() => {
        console.log('Component mounted');

        return () => {
        console.log('Component unmounted');
        };
    }, []); // Empty array ensures this runs only once after the initial render

    return <div>My Component</div>;
    };

    export default MyComponent;
---

### How do you create a Context?
#### First, create the context

    import React, { createContext, useState } from 'react';

    // Create AuthContext with default value
    const AuthContext = createContext(null);

    export default AuthContext;

#### Provide the context 
Next, create a provider component that will wrap your application and provide the authentication state.

    import React, { useState } from 'react';
    import AuthContext from './AuthContext';

    const AuthProvider = ({ children }) => {
    const [user, setUser] = useState(null);

    const login = (userData) => {
        setUser(userData);
    };

    const logout = () => {
        setUser(null);
    };

    return (
        <AuthContext.Provider value={{ user, login, logout }}>
        {children}
        </AuthContext.Provider>
    );
    };

    export default AuthProvider;

#### Consume the context
    import React, { useContext } from 'react';
    import AuthContext from './AuthContext';

    const UserProfile = () => {
    const { user, login, logout } = useContext(AuthContext);

    return (
        <div>
        {user ? (
            <>
            <p>Welcome, {user.name}!</p>
            <button onClick={logout}>Logout</button>
            </>
        ) : (
            <button onClick={() => login({ name: 'John Doe' })}>Login</button>
        )}
        </div>
    );
    };

    export default UserProfile;

#### Lastly, Wrap your App to provide the context to all components.
    import React from 'react';
    import ReactDOM from 'react-dom';
    import App from './App';
    import AuthProvider from './AuthProvider';

    ReactDOM.render(
    <AuthProvider>
        <App />
    </AuthProvider>,
    document.getElementById('root')
    );

### What is NextJS?


