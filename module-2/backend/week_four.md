## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?
   a cookie is a small piece of information (string < 4kb) used to store state between client and server
2. What’s the difference between a session and a cookie?
  a session is a servers way of keeping state and is typically done on the server side (not the case with ruby)
3. What’s a flash and when do you want to use flashes?
flashes are messages used to alert the user when an action was performed or could not be performed
4. Why do people say “HTTP is stateless”?
  HTTP is stateless because each request does not know anything about any other request or response - that said cookies and sessions are ways of giving the client-server relationship state
5. What’s authentication? Explain.
You are who you say you are - It is the servers way of knowing that a user is who they claim to be, with this in place special access and privileges can then be given to an authenticated user
6. What’s the difference between authentication and authorization?
authentication is the process of verifying that a user is who they say they are while authorization is the process of giving special privileges to certain types of users, visitor - default - admin, etc.
7. What’s a before filter?
a before filter is a method run before each action within a controller - this typically involves checking session info to verify that it is the expected user accessing a resource
8. How do we keep track of a user once they’ve logged in?
we start a session in ruby - which gives the user a 'session id' of sorts - this session id is maintained until the user logs out, clears cache, or exits the browser, and is used to give them access to resources based on their level of authorization
9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
you want to namespace a resource that is only accessible for certain levels of authorization
you want to nest a resource if it has a parent resource that it belongs to
namespacing will 'nest' the chosen resource under a parent that is itself not a resource - for instance /admin/categories - if you wanted only admins to access categories index, whereas you would do /dreams/:id/categories where a categories belonged to a dream
10. At a high level, what tools can you use to implement authorization? How would you use them?
    bcrypt is an example of a hashing tool we use to encrypt a users password, it allows us to store an irreversible code in our databases instead of the actual password.  This is an example of hashing, where an extremely complex algorithm is used to convert the password by salting it, which can be stored and used to verify a user.
11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
    An enum is stored in the model and is a way to map integers stored in a database to other datatypes such as a string
12. What are some strategies you can use to keep your views DRY?
    You can confine logic to your models and use conditionals to ensure only proper users are accessing views

### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]
```  

given.map { |hash| hash[:holiday][:name] }.sort


14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?
given.delete('$').to_i

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
