1. How do we make flash messages display on a page?
There are two steps, add it to the controller and then add to the HTML file for the application. You should add the the following code to the Application.html.erb file and it should be placed below the nav bar tags in the body section of the file:
<% flash.each do |type, message| %>
  <%= content_tag :div, message, class: type %>
<% end %>

2. Where is cart information/temporary information usually stored?
We store it in a session and the cart model is a PORO( plain old ruby object) in our model. This is because we do not want to store the information in our database.

3. What might be some reasons not to store cart in our database? Are there any reasons why we would want to persist that information?
 We don't want to create objects that are in the data until someone actually checks out on the transaction. If we stored the information in the database then it could cause the following issues:
  1. it could cause multiple updates and create many points where the user needs to go into the model as they delete or update their cart.
  2. the user would need to be logged in or at least identified for the item to be properly associated and stored in the database. So this would limit it to just registered and logged in users.
  3. there is a potential for abandoned records is the user decides to not finalize the cart into an order.

  We do want to persist the information though until the user is ready to finalize the transaction and need to know things like the amount of items etc, as well as have methods that total the cart amount and price.

4. What is the purpose of the asset pipeline?
  Assets are things in our application like stlyesheets, css, images etc. The asset pipeline is a rails feature that is responsible for compressing, minimizing, and serving up our public folder. The first feature is that is concatenates assets, which reduces the number of requests our browser needs to make to our application to render a web page. The next feature is minification, which removes the white space and comments in our css files. Lastly, it allows for us to use higher-level languages like Sass for css, coffescript for javascript, and ERB for ruby and does the precompiling to html work. The asset pipeline  prepares our application so our browser can efficiently read our assets in a production state and makes our application faster.

5. Why do we precompile our assets?
  Precompiling our assets lets us use higher-level languages like Sass, ERB, and coffescript. There are several reasons why you might want to precompile your assets locally. Among them are:

  You may not have write access to your production file system.
  You may be deploying to more than one server, and want to avoid duplication of work.
  You may be doing frequent deploys that do not include asset changes.
  Local compilation allows you to commit the compiled files into source control, and deploy as normal.


6. What do each of the following tags do?
These are all actionview helpers which provide methods to generate html that links to assets in our application.

```ruby
<%= stylesheet_link_tag "application" %> this is the html # => <link href="/assets/style.css" media="screen" rel="stylesheet" />
this is the manifest file that directs the order in which to load and combine all the css files in the application and reduces load time.
<%= javascript_include_tag "application" %> this is the manifest file for loading the javascript files in the application.
<%= image_tag "rails.png" %> this returns the html image tag for the source of the asset.
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
 A good readme should be written concisely, so the user can quickly understand the application and is drawn in to keep reading the documentation. Elements that are important to include in a Readme are links to any other documentation or gems in the application. How to get started with the application- so any gems that need to be installed. It is good to provide code examples. It is also good to include any persistent issues as well as dependencies. The last recommended piece is to include badges.

 A good practice to deploy is Readme driven development, which helps keep to original scale and scope of the application.

8. What are the top four accessibility issues that we as developers should be aware of?
  Visual- this is ensuring that our application can be experienced well both with sight and with a screen reader. It is also important to look at our application through a color-blind lens to ensure that color choice is accessible for a larger population.

  Mobility-  is an issue where the user typically has difficulty using a mouse or a trackpad. The first and easiest thing we can do as developers is make sure we are making our application completely usable with just a keyboard.

  Cognition- this is a complex issue to address, but we as developers should think about how we organize content on our pages that is easier to follow and follows patterns. it is good to think about providing content in multiple forms, use proper headings, indexes etc.

  Hearing- this would be making sure there is transcript for any audio aspects our our applicaiton.

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
  It is an example of a Callback. Callbacks are hooks into the life cycle of an Active Record object that allow you to trigger logic before or after an alteration of the object state. The before_save should be in our models.

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```
scope :user, -> { where(active: true) }

11. What is the difference between a scope and a class method?
Scopes and Class methods are very similar, however are less error prone. One advantage is that they do not return a nil value and instead return a blank activerecord object. A Scope will also always return a relation, where as a class method will not. Scopes are always chainable. 
