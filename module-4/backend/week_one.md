## Week One - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR.

1. What's the most useful thing you learned from completing the intermission week work?
  The CharacterCount and Fibonacci exercise in the Javascript without Browser section was pretty helpful. It was helpful to draw parallels of using JavaScript to write logically methods similar to ruby-- ie. practice with loops, iterating over arrays, testing, etc.

2. What are some tools to help debug JavaScript code?
    console.log => Using the console.log in the code to see what the value is.
    pryjs => when executing code in the terminal- it acts like pry in ruby
    debugger => put in the code and then it allows you to pause the code in the browser and see the current values, etc.
    browser inspector => tons of tools in the element tab (good for debugging html and css work), console tab (where we can print out values, errors, etc.), source tab( debugging javascript- call stack, global variables, can use breaks, etc. ), and networking tab( shows requests and responses).

3. What are some tools you need in order to unit test your JavaScript?
    Mocha and Chai-- popular assertion library. Need to export methods and import in test files to run test suite.

4. What is the syntax for invoking a function?
    function() if there is a parameter then function(parameter)

5. What's `this` in JavaScript?

  It is Javascript's context variable. If it is in the global context it is the global object- the window. in other contexts, it refers to the context in which a function was invoked in JavaScript. Keep in mind that this is different from where it was defined.

6. What is Webpack and why is it useful?
  Webpack is a Node package that digs through your assets, finds dependencies, and spits out a single JS file that is ready for production. It is similar to the Asset Pipeline in Rails, in that it is a build tool.

7. When/why do you want to use event delegation?
  Event delegation refers to the process of using event propagation (bubbling) to handle events at a higher level in the DOM than the element on which the event originated. It allows us to attach a single event listener for elements that exist now or in the future.
  We have been using it a lot in Quantified self, because we are pulling the data from an API- so it does not know what the input fields are yet. This is also a concept that is good for adding or creating items and wanting them to have the same behavior.

8. What's `npm` and what do we use it for?
  It is the Node Package Manager. We use it to install packages and run packages.

#### Review  
9. What's the MVC design pattern? Describe each part of MVC.
  It is a common way to set up a rails application. It organizes it so that the model, view, and controller have certain roles in the delivering information and working with the browser.
  M-Model: The are the Ruby Classes. This is where the business logic sits and is the blueprints for the different classes arnd it talks to the database.
  V-View: This is what the user sees. It is the HTML, CSS, Etc. There shouldn't be any logic in the views and just read what the controller specifies.
  C-Controller. Handles the browsers requests and pulls the appropriate information from the models as well as gives it the the views.

10. What are a few ways to optimize a Rails application?
  Use New Relic to run a diagnostic on the application.
  Look for N+1 queries, a solution is using an include to limit the amount of time you go back to the database.
  Caching and memorizing- API calls, etc.

11. What's a background worker? When would we want to use a background worker?
A background worker is used is you have a job queue- some examples would be sending an email, sweeping caches, pulling data from a 3rd party api. 
