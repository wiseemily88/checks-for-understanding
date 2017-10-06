## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

1. List the five common HTTP verbs and what the purpose is of each verb.

  get, post, delete, patch, put
2. What is Sinatra?

  It is a Rake or middleware that uses Ruby that allows us to respond and create HTTP requests.
4. What is MVC?

Model, View, anld Controller. It is the way we should organize our web application code. The model holds the classes, validations and business logic. The views are the HTML code that renders the expected output. The Controller or controllers interprets the http request and directs to the views and is able to pull the logic from the models.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
Because it is REstful, which is a common best practice for creating our web applications.

6. What types of variables are accessible in our view templates without explicitly passing them?
Instance variables - guess based on below you can do local variables too but i am not sure

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    @count = Horses.all.count

    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
I am not sure- i need to further read about local variable and passing between controller and views.

9. What's the purpose of ERB?
  The ERB is embedded ruby, which allows us to us html and ruby to render what we want on the page.

10. Why do I need a development AND test database?
  You want a test database so you can test if you can update, delete, etc. data, but you don't want to actually maninpulate the database. The development database should mimic what the database will be in production.

11. What is CRUD and why is it important?
  CRUD stands for Create, Review, Update, and Delete. It is the most common interactions users will have with the web applications, and it is the basis for most user stories.

12. What does HTTP stand for?
  Hypertext, something.. Protocol

13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  <%> or <%=> the first way will not include the ruby in the view and the second will render on the page.
14. What's an ORM?
  Object Relational Mapper, we are using ActiveRecord as our ORM. But is helps us create, and manage data and parse into tables, and map how the data is connected.

15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
  ActiveRecord
16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
  1. get '/restaurants' do
    @restaurants = Restaurants.all
     erb :index
    end
    * this allows the user to read all the restaurants

    2. get '/restaurants/:id' do
    @restaurant = Restaurants.find(params[:id])

    erb :show
    end
     * This allows you to view one restaurant

     3. get '/restaurants/new' do
     erb: new
     * this is to show to new page to create a new record.

   4. post '/restaurants' do
      @restaurant = Restaurant.create(param[:restaurant])
      erb: index or show.#{show.id}
      end
    * this is to create the new restaurant

  5.  get '/restaurants/:id/edit' do
      @restaurant = Restaurant.find_by(param[:id])
      erb: show
      end
    * takes this to the edit page

  6. patch '/restaurants/:id'  do
      Restaurant.update(params[:restaurant], id)

      redirect '/restaurants/:id'
      end
    * this updates the restaurant page

  7. delete '/restaurants/:id' do
      Restaurants.delete(id)

      redirect '/restaurants'
      end  

    * this delete   


17. What's a migration?
  A migration is the way to set up how you want the data in the database, as in columns, data type etc.

18. When you create a migration, does it automatically modify your database?
  No, you need to run the the DB: create to re-seed.

19. How does a model relate to a database?
The model is the classes and business logic of our application. The model is still the blueprint for how we want our objects to be created based on the database. It is the code that interacts with the objects that Activerecord helps to create instances of objects for each row of code. The columns in the table are the attributes of the class. The model also holds the validations of the attributes and the connections to other tables in the database

20. What is the difference between `#new` and `#create`?
New does not save in the database and create makes one but also saves it.
