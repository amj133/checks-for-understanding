## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
ActiveRecord is an ORM (object relational mapper) that allows programmers to interact with the data within their database.  As an ORM, each row within a table is treated as an object within ruby, and each column within the table is an attribute of the object.  This allows users to access and interact with their database information as if it were other ruby objects.
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
#all, #joins, #group, #order, #first, #last
These methods are defined within ActiveRecord, which our class is inherting from.  The class Team represents a Teams table, and each row within that table would be an instance of Team.  

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
Team.find(4)
Team.where(owner_id = Team.find(4).owner_id)

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
Team.find(4).owner

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
Assuming we are not talking about elementary school, there will be a many to many relationship between students and teachers.
A student will have many teachers, and a teacher will have many students.
(description of schema diagram)
  +Students (name of table)
    -first_name, last_name, expected_graduation (all columns)
  +Teachers (name of table)
    -first_name, last_name, first_year_teaching (all columns)
  +TeacherStudents (name of join table)
    -student_id, teacher_id, subject (all columns)
    
6. Define foreign key, primary key, and schema.
  A primary key is a unique identifier for a given table.  Each row of a table has a unique primary key, this could be an incrementing integer, it could be a different attribute that is unique to the row, or it could be a combination of attributes.  
  A foreign key is associated with the primary key of a separate table.  For instance, in the join table created in question 5, the student_id column is the foreign key within the TeacherStudents table because it is composed of primary key values from the Students table.  Because a student can have multiple teachers, the same student_id may appear for multiple rows within the TeacherStudents table.  
  
7. Describe the relationship between a foreign key on one table and a primary key on another table.
A foreign key is always composed of primary key values from another table.  A given primary key can occur in multiple rows as a foreign key.  See answer to question 6 for example.

8. What are the parts of an HTTP response?
head, body
head consists of important key-value information about the resonposne, VERB, PATH, PROTOCOL (line 1) along with additional useful information such as format, content length, etc.
The body is the actual text information that will be displayed in the browser, or that is used to link to assets that will then be displayed.

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
3. What two columns does `t.timestamps null: false` create in our database?
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
6. Give an example of when you might want to store information besides ids on a join table.
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?
