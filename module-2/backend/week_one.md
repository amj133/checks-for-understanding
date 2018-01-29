## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
  GET - retrieve a resource
  POST - create new resource
  DELETE - delete a resource
  PUT - edit all of an existing resource
  PATCH - edit part of an existing resource
2. What is Sinatra?
  Sinatra is a light-weight web application framework that uses the MVC model for routing requests and responses
4. What is MVC?
  MVC stands for Model View Controller and is a structure for designing web applications that delineates specific responsibilities to these three components - the controller being the 'overlord' that communicates with the user (indirectly through the server) and delineates tasks to the model and view appropriately to return the requested resource the user or perform the specified action 
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
We follow conventions in order to understand what the user is attempting to do with a given http request
6. What types of variables are accessible in our view templates without explicitly passing them?
instance variables - local variables must be explicitly passed from the controller
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  @count = 1
  Then within index.erb you can use @count
  
  ```ruby
  get '/horses' do
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
  name = 'Mr. Ed'
  erb :index, {:locals, name => :name}
9. What's the purpose of ERB?
  ERB stands for embedded ruby and allows us to render pages with ruby code in it - we can explicity display the return value of a given piece of code or just run the ruby cody itself (e.g. conditionals)
10. Why do I need a development AND test database?
Because within our tests we often want to try editing, deleting, and adding new data to our databases - we would not want to continually edit our actual (development) database while executing these tests - furthermore we use a database cleaner to remove and data added to the database after a given test.
11. What is CRUD and why is it important?
Create Read Update Delete - it is the fundamental functionality that should occur between the user of an application and data stored within a database
12. What does HTTP stand for? 
hypter text transfer protocol
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
<%= %> This will render whatever the return value within the brackets is
<% %> This will run the ruby code within the brackets but will not render it within the html
14. What's an ORM?
Object Relational Mapper - it is a model for creating instances of objects that represent the rows within a database.  The class generally represents a table within a dB and an instance of the class represents a row within that table.
15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
Active Record
16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
 get / - root for showing the home page/dashboard
 get /restaurants - shows an index of all the restaurants
 get /restaurants/new - bring user to form to create new restaurant
 post /restaurant - add newly created restaurant to index
 delete /restaurant/id - user can delete individual restaurant
 get restaurant/id/edit - bring user to form to edit existing restaurant
 put /restaurant/id - user can edit existing individual restaurant
 
17. What's a migration? 
a migration is the blueprint used for creating a table within a database - what pieces of data it will contain 
18. When you create a migration, does it automatically modify your database?
no - the migration has to be run
19. How does a model relate to a database?
a model represents a table within a database - whereby the class represents the table, and an instance of the class represents a row within that table
20. What is the difference between `#new` and `#create`?
new will create an instance of the model - but not save it to the database
create is new and save - an instance of the model is created and saved to the database

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
within the seed file:
  films = CSV.open('/films.csv', headers: true, header_converters: :symbol)
  films.each do |row|
    Film.create(id: row[:id], title: row[:title], description: row[:description])
  end 
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores'] 
}}
```
How would I add 'granola bar' to things you should have when hiking?
activities[:hiking][:supplies].push('granola bar')
23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
encapsulation - protection of an objects state from functions/objects that do not need access to it
polymorphism - similar methods with slightly different functionality
abstraction - outline of object state/methods and what makes it unique
inheritance - classes can have sub-classes to prevent redundancy and create a hierarchy

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources - EXCEPT LAST QUESTION!!!

Choose One:
* I feel comfortable with the content presented this week
