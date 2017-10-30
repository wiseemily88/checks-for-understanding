## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?
It is what gives state with certain web side interactions. It is usually the client side, and holds small (5 kil bites) pieces of information and is stored on the user's computer.

* What’s the difference between a session and a cookie?
  Sessions are always on the server, where as cookies are generally tied to the web browser and client's machine. They store small amounts of data that can be persisted in the controller.

* What’s a flash and when do you want to use flashes?
  It is cleared after each request, and are useful for displaying messages.

* Why do people say “HTTP is stateless”?
  Information does not persist between requests.

* What’s authentication? Explain.
  Is the act of making sure the user is who they say they are. We specifically used tools bcrypt to verify the user has a secure and correct password.

* What’s the difference between authentication and authorization?
  authorization is making sure that only specific users/ admins can see and act with the correct parts of the ap
* What’s a before filter?
It dictates actions or methods that need to be run first. Example from class was verifying the current user is logged in.

* How do we keep track of a user once they’ve logged in?
  using Sessions helps to keep track of the user.

* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
namespace is good for organization, like an admin- but you don't need an additional id for it like a nested resource.

* At a high level, what tools can you use to implement authorization? How would you use them?
- enum ( this helps to translate roles for users)
-namespace - for organizing views and controllers based on roles
- before_action
-inheritance
* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
It is what helps you define roles. You can access methods. like user.admin? and it will return true or false.
* What are some strategies you can use to keep your views DRY?
You can use partials
