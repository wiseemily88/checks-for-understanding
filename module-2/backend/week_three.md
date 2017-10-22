## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?

  Rails new project name
2. What do Models generally inherit from in rails?

  ApplicationRecord
3. What do Controllers generally inherit from in a rails project?

  ApplicationController
4. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

  In the route file in the config folder:

  resources :horses, only: [:show] do
  end
5. What rake task is useful when looking at routes, and what information does it give you?

  Rake/ Rails Routes. It gives you all the current routes in your application. You get the prefix, URI, controller and action for each route.

6. What is an example of a route helper? When would you use them?

  new_horse_path it is the prefix word path. It also lets you know if a path needs an additional object, like an id. You would use them in your controllers to redirect, in a test, or in your views.

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

  The URL is the absolute path and the path is the relative path.
8. What are strong params and why are the necessary?

  Strong params are required with Actioncontroller for updating or creating new resources. It helps to ensure that we are passing through correct information into our models.

9. What role does `form_for` play in helping us create our forms?

  This is a a Rails helper for creating forms that render HTML with less tedious code.

10. How does `form_for` know where to submit the user's input?

  Based on the instance variable that is passed in as the path, it knows if it is an update or a new based on the value, which determines what is rendered after.
11. Create a form using a `form_for` helper to create a new `Horse`.

    <%= form_for @horse do |f| %>
    <%= f.label :name %>
    <%= f.text_area :name %>
    <%= f.label :breed %>
    <%= f.text_area :breed %>
    <%= f.submit "create a horse" %>
    <% end %>
12. Why do we want to validate our models?

  To ensure that we are passing in correct data and saving in the database, ie correct form, not empty, etc.
