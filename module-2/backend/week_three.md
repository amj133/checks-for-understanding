## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
    rails new <app-name> -T -d="postgresql" --skip-turbo --skip-spring
2. What do Models generally inherit from in rails?
    < ApplicationRecord
3. What do Controllers generally inherit from in a rails project?
    < ApplicationController
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
    resources :horses, only: [:show]
5. What rake task is useful when looking at routes, and what information does it give you?
    rails routes - will give you a list of prefixes, uri's, and the controller#action that utilizes them
6. What is an example of a route helper? When would you use them?
    horses_path - you use them in leiu of an explicit relative path - this is useful when you want a redirect to an individual resource where its path is specific to its id
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
    path will give you the relative route while url will give you the full url including domain name
8. What are strong params and why are they necessary?
  strong params only permit certain parameters from being able to be assigned in mass - helping to prevent
  security threats from users without admin privileges 'posing' as those with them
9. What role does `form_for` play in helping us create our forms?
    form_for is a helper method that sets up the html for a form for us - all we have to do is specify
    the label and input type/value it is being assigned to
10. How does `form_for` know where to submit the user's input?
    based on the arguments it is passed e.g. form_for(@horse) will submit to horse_path(@horse)
11. Create a form using a `form_for` helper to create a new `Horse`.
      <%= form_for(@horse) do |f| %>
        <%= f.label :name %>
        <%= f.text_field :name %>

        <%= f.submit %>
      <% end %>
12. Why do we want to validate our models?
      to make sure that certain resources cannot be created without necessary attributes
13. What are the steps of the DNS lookup?
      First the browser looks in its local cache to see if it has the ip address associated with the domain name specified.  If it doesn't it then goes to a local DNS server to see if other people in the area have looked up the same domain name.  If it can't find it there it goes to a regional DNS server, then higher and higher up the lookup chain while you patiently wait.

### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
    def move
      prance
    end
15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?  
      furniture[:purchased] => true
      furniture[:table][:height] => 3
16. What is inheritance?
  Inheritance is a way in which a class in Ruby can utilize methods from another class.  When class a inherits from class b, class a can now call any method created in class b on an instance of class a.  Another way to say it would be the behavior of one class is completely contained within its child class.  For instance, class Rat is a child of class Mammal, and inherits all of the behavior of the Mammal class.

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few
  Strong Params - had to lookup to clarify - helpful to see how people hack in as admin

Choose One:
* I feel confident about the content presented this week
