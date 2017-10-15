## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
ActiveRecord is Rails ORM and lives in the M part of the MVC. It allows us to pull in data from our database and create ruby objects out of them. ActiveRecord also allows us to set up associations of tables in our models and validate data in our models. There are also many methods that we inherit with ActiveRecord that are like SQL requests that we can use on the ruby objects (.join, .maximum, etc. ).

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
.join, .average, .find, .create, .update, .maximum, .minimum, .group, .pluck
We can call these methods because we are inheriting from the ActiveRecord Base model.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

team_4 = Team.find(4)
Owner_id = team_4.owner_id << and then I believe you would need to create a table for owners and a reference to Team so we could find out the name of the owner- right now there is not connection so you can not find the name from team. you would need to do something like this

Owner_name = Owner.find(owner_id)

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

Team.find(4).owner.name

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

It is a many to many

class Student
  has_many :courses
  has_many :teachers, through: :courses
end

class Course
  belongs_to :teacher
  belongs_to :student
end

class Teacher
  has_many :courses
  has_many :students, through: :courses
end


  create_table "students", force: :cascade do |t|
    t.string "name"
  end


  create_table "teachers", force: :cascade do |t|
    t.name "name"
  end

  create_table "courses", force: :cascade do |t|
       t.belongs_to :student, index: true
       t.belongs_to :teacher, index: true
     end

6. Define foreign key, primary key, and schema.

  A Foreign key is the id or the identifier for how the tables are linked. The foreign key refers the the primary key on the associated table. The primary key is the unique or combined attributes that identify the table. Unless specified it is the id.

  not sure what the schema looks like ?

  * add_foreign_key 'books', 'authors'

7. Describe the relationship between a foreign key on one table and a primary key on another table.
  The foreign key is the primary key of the other table.
8. What are the parts of an HTTP response?
  Status- code like 404, 202, etc.
  Header- Key/value pair
  Body - html/css


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
.where (some attribute) => it returns an array on objects that match the specified given criteria
.group( some attribute).count => returns a hash where the key is the attribute and the value is the count
.find(:id) => returns the object related to that id
.join(:some table) => creates a joined table saved in memory that you can further query
.minimum and .maximum(some attribute) => returns the highest or lowest object

2. Name your three favorite ActiveRecord rake tasks and describe what they do.
rake db:drop - drops the database
rake db:create - creates the datbase
rake db: migrate - sets the migrations

3. What two columns does `t.timestamps null: false` create in our database?
created_at and updated_at

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
Many to many

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
  I created a course table that would hold both the ids or the teachers and the students.

6. Give an example of when you might want to store information besides ids on a join table.
  in the case of the example above the name of the courses.

7. Describe and diagram the relationship between patients and doctors.
  many to many linked through appointments.

  class Patient
    has_many :appointments
    has_many :doctors, through: :appointments
  end

  class Appointment
    belongs_to :doctor
    belongs_to :patient
  end

  class Doctor
    has_many :appointments
    has_many :patients, through: :appointments
  end

8. Describe and diagram the relationship between museums and original_paintings.
  class Museum
    has_many :original_paintings
  end

  class Original_painting
    belongs_to :museum
  end

9. What could you see in your code that would make you think you might want to create a partial?
  If you have views that have identical code you can cut it out and have it render partial
