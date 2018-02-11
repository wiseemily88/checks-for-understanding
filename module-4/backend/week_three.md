## Week Three - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR.

1. At a high level, what is Node?
  Node is a server framework, that uses JavaScript on the server. Node uses asynchronous programming- which means that it does not wait for the file content to be delivered, it goes to the next request. Its non-blocking and single threaded nature, make node very lightweight and memory efficient.

2. What is Express? What is Express similar to in the Ruby world?
  Express is similar to Sinatra. It is a web framework. It is relatively minimal with many features available as plugins.

3. How do we setup a route when creating an API with Node and Express? Please provide a code snippet.
```
app.METHOD(PATH, HANDLER)
```
Where:
- app is an instance of express.
- METHOD is an HTTP request method, in lowercase.
- PATH is a path on the server.
- HANDLER is the function executed when the route is matched.

```
app.get('/users', function(req, res, next){
  res.send("View all users")
})
```

4. What do we use Knex for?
  Knex is the used to interact with our SQL database. It is similar to activerecord in that it provides a layer and methods to query, build schema, run migrations, etc. and allows us to adjust underlying database from sqllite to mysql for example without having to adjust the code.

5. How could you organize your code to follow the MVC design pattern in your Quantified Self project?
  We can build methods that act like a "controller". So the methods work with the request and pull out/ save etc. any necessary information and then give the correct response. The controller file can also take the responsibility of error handling. A "model" file can be responsible for interacting and querying the database.  The views would be the HTML files.

6. How do you execute raw SQL in node?
  We use Knex. and then can use the method. "raw".

7. What are some advantages to having your front end and back end code live in separate applications? What are some disadvantages?
Pros:
- Modularity: allows you to change/ build the application at different paces
- Right language for the job: choosing a front-end and back-end language or framework for each role lets you optimize your stack.
- Builds / Deployment: not only can you develop at different paces, you can now come up with testing, build, and deploy strategies that are separate.
- API: this methodology forces you to think like an API developer which has tremendous benefits for your users and, potentially, external developers and businesses (depending on your product offering).

Cons:

- Builds / Deployments: you must now come up with independent testing, build, and deployment strategies for your application separated by front and back-end, which takes time and resources.


#### Review  

8. Describe DNS.
  Is the Domain Name Server is like the web's version of a phonebook. They hold all the domain name and ip address pairs. IP addresses are how computers talk, but are very hard for humans to remember. So the Domain name ("human friendly") links to the a computer IP address.

9. What does writing clean code mean to you?
  Writing clean code:
  - Clear variables and methods: uses descriptive variables and method names that are obvious to other developers what the method is doing.
  - Clean syntax: Debugger, non why comments, whitespace, etc. are removed
  - Follows language conventions: so in JavaScript uses camel case, etc.
  - Single responsibility: Methods and functions are responsibility for one thing, and this also allows functions to be used more frequently throughout the application.
  - In the language allows for OOP style programming: Code is organized with like behaviors and state.
  - code is tested :)

10. If you were building an application that models hotels, what classes would you need? What classes would be responsible for what functionality?
  - Class Room
    State: number, type, vacant or occupied?, number of beds
    Behavior: occupied?, clean?

  - class HotelGuest
    state: number in party, name,

  - class Reservation
    state: Date, hotelGuest id, room id
    this is a joins table between room and HotelGuest
