# ITransition Study Guide
---
### Differences between Var, Let and Const
Var: Function-scoped or global if declared outside function. Are reassignable and will initialize as undefined. If you reference them before initialization it will not return an error but undefined.

Let: Block-scoped (limited to the block is declared). Can be reassignable and this type of variable is not initialized until the declaration is encountered. Accessing it before declaration results in ReferenceError.

Const: Block-scoped and cannot be reassigned after its initial assignment. If the variable holds an object or an array it can be modified, also needs to be initialuzed until declaration.

### Difference between HTML, CSS and JavaScript
HTML (Hypertext Markup Language): It's the structure of a webpage. Think of it as the skeleton of a house. HTML defines the different parts of a webpage (like headings, paragraphs, images, etc.). It gives meaning to the content, but by itself, it's pretty plain and unstyled.

CSS (Cascading Style Sheets): It’s the design or style of a webpage. If HTML is the skeleton of a house, CSS is the paint, furniture, and decorations that make it look good. CSS controls things like colors, fonts, spacing, and layout, making the webpage visually appealing.

JavaScript: It’s the behavior or functionality of a webpage. If HTML is the skeleton and CSS is the style, JavaScript adds the interactive features, like doors that open, lights that turn on, or buttons that perform actions. It lets you make the webpage dynamic and respond to user interactions (e.g., clicking, scrolling, submitting forms).

In summary, HTML builds the structure, CSS makes it look good, and JavaScript makes it interactive.


### HTML Basic Boilerplate

    <html lang="en"> 
        <head>
        <meta charset="UTF-8">
        <meta name="viewport">
        <title>Document</title>
        </head>
        <body></body>
    </html>

