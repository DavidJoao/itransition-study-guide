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

### What is NextJS?


