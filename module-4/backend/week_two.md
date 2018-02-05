## Week Two - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR.

1. What's one difference between ES5 and ES6?
- ES6 has more syntax sugar built in, particularly around defining functions using the arrow function.
-- ES5 array.map(function() {
    code here..
    });

-- ES6 array.map(( => {
  });

- ES6 also introduces the class syntax to define constructors that mimic classes with OOP. The functionality and use is the same, but the syntax is reminiscent to other class structures.

- Const and Let( const can't be reset) and let is scoped to the block it is in is part of ES6. ES5 uses var.

2. What's the difference between asynchronous and synchronous JavaScript?
  - Anynchronous javascript takes advantages of multiple threads and the queue to execute code in the browsers out of order or  execute a piece of code before a function may be done running. This is particularly valuable with loading data from APIs, or having multiple functions that needs to occur.  By nature Javascript is a synchronous language.

3. What are the four pillars of Object Oriented programming?
  - Encapsulation- which is the principle of grouping like state and behavior together. An example would be placing behavior and state in classes.
  - Abstraction- is the principle where you remove some of the logic and details that the users/ or programmers doesn't need to see or know to be able to run the program. It makes the implementation of a complex application a lot easier. You just need to know about the methods available and not have to worry about the implementation under the hood. It allows us to implement software that’s highly reusable and easy to understand.
  - inheritance - is the principle that the is a child parent inheritance. It allows us to create classes and subclasses and have access to properties in our subclasses from the parent classes. It reduces development time and ensures consistency in coding.
  - polymorphism - is the principle that you can present the same interface for differing underlying forms. Polymorphism is used to make applications more modular and extensible. Instead of messy conditional statements describing different courses of action, you create interchangeable objects that you select based on your needs.

4. What are some tools available in JavaScript to help you write object oriented code?
- constructors act similar to classes and allows us to Encapsulate specific behavior that should belong to objects.
- prototypal inheritance

5. What are some key concepts to be aware of when refactoring your JavaScript?
- low hanging fruit- poorly named variables, inconsistent whitespace and semicolons, debuggers, etc.
- comments in code- made sure they are the why and not the what
- long methods that are doing multiple things like fetch a call, manipulate the dom, etc..
- long parameters lists
- duplicated code
- complex conditional statements

6. What's a callback function and what are some reasons when we use/need callback functions?
- a callback is a second function that is being passed to another function as a parameter. We use callbacks with event listeners- so a click or other event action evokes a function. We can also use them for asynchronous behavior using a setimeout().
7. What's the scope of variables in Javascript?
- global scope is outside of a function or block in your program.
- local scope is defined within the function
- intermediate of block scope with let. It is scoped only to the block of code.

8. What's the difference between `==` and `===` in JavaScript?
- == is equal, after type conversions
- === is strict equal

9. Why do front end frameworks exist?
-- Keep state out of the DOM
-- Higher-level abstractions
-- Code organization

#### Review  

10. Why do people say "HTTP is stateless"?
- it is stateless because the information is only held on for the length of the specific request. Data and information does not persist in between request cycles.
11. Describe a RESTful API.
- a restful API is one that uses is an application that uses REST architectural type to respond to specific HTTP requests. They use GET to retrieve a resource; PUT to change the state of or update a resource, which can be an object, file or block; POST to create that resource; and DELETE to remove it.

12. What are some main characteristics of a team following an agile workflow?
- have small defined sprints typically 2 weeks to get a small piece of functionality complete and then get feedback to keep iterating
- you would expect there to be stand ups to ensure there are no backlogs and the everyone is aligned on the sprint and retros.
- many organizations use Scrum or kanban to implement agile workflow

13. What are some advantages **and** disadvantages to using OAuth to authenticate a user?
- advantages- you are putting the security in a larger user that has more resources to deal with authenticating users. you can also get access to other apis at times using their oauth.
- disadvantage less control, and then you have to be thoughtful that you have the correct accounts to not deter users.
