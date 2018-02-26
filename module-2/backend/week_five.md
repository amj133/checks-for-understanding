### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?
we create a flash message in our controller with flash.notice and then we display the flash notice in a view, typically the application layout

2. Where is cart information/temporary information usually stored?
within a session on the client side, something like session[:cart]

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
It saves space in our database not to store the cart there and it saves memory by not having to retrieve the cart information from the database.  Furthermore, carts are something that change frequently and are only temporary until a client checks out their cart, thereby creating an order.  We may want it to persist in instances where we want a user to be able to close the browser/log out, then open the browser, login, and still have their cart in tact, such as with amazon.

4. What is the purpose of the asset pipeline?
The purpose of the asset pipeline is to prepare content such that it can be easily transferred between the server and a browser, this typically involves concatenating and compressing files.  This helps save communication time between a browser and server by allowing the server to ship all assets in one or as few responses as possible.

5. Why do we precompile our assets?
In addition to the concatenation and compression mentioned above, we precompile our assets so that the browser can cache the assets and check with the server to see if any of the content of an asset has changed.  If it has not, then the browser will load the content from the cache, thereby saving time.

6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>
allows the html to reference a stylesheet for styling purposes
<%= javascript_include_tag "application" %>
allows the htmlt to reference javascript for animation purposes
provides
<%= image_tag "rails.png" %>
accesses an image asset in the appropriate location, which will be in the public folder within production
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
Purpose/ reason/ expected results
Setup & Installation
Executing / Common Applications of the app
Troubleshooting, common issues
Contributors
Readme's will make the application more usable for users and developers

8. What are the top four accessibility issues that we as developers should be aware of?
visual impairment
color-blindness
audio impairment
mobility

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
this is an example of a callback - this would be found within our application controller and is used to implement some logic before or after altering an object's state

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```

11. What is the difference between a scope and a class method?
a scope is used to return another scope, which is a collection of objects.  In this sense a scope expresses intent by saying, you should always expect a collection to return when calling this.  Scopes are often chained off of, and are building blocks in that way.  A class method can return a number of things, such as a collection of objects or nil.

### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?
  a[:cart]["48"] = 4
  12b. How would you increase the quantity of item 29?  
  a[:cart]["29"] += 1
  12c. How would you find out how many items your user is thinking about purchasing?   
  a[:cart].values.sum
13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?  
polymorphism is providing a common interface for various underlying data types.  For example, different types of numbers such as floats and bigdecimal can behave together with common mathematical methods and are therefore polymorphic.  When you define a class in ruby you can create different instances of the class that share the same behavior, and therefore achieve polymorphism.  Duck typing in rails refers to the treatment of objects based on what they can do more than what class they are or where they inherit from.  Active Record relations are a great example of this, they return AR relations which have a lot of similar behavior as arrays, and in this sense can be treated as if they are arrays.

14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
a.gsub("(", "").gsub(/\) |-/, ".")

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
