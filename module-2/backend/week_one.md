## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
- POST - create new things usually into a database
- GET - read or fetch things from database 
- PUT - update all of an existing thing in database
- PATCH - update part of an existing thing in database
- DELETE - delete things from database

2. What is Sinatra?
- Web framework that can send/receive HTTP responses and convert ruby into HTML

3. What is MVC?
- Model - data logic/calculations and interacts with databases
- View - page layouts and templates, generally in HTML
- Controller - traffic cop to manage HTTP requests and call Models if databse info is needed prior to then handing that information off to the Views to generate the pages

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
- It makes our code more readable and easier to understand for future developers.

5. What types of variables are accessible in our view templates without explicitly passing them?
- Instance variables

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

```ruby
  get '/horses' do
    @count = 1
    @name = 'Mr. Ed'
    erb :index
  end
  ```

8. What's the purpose of ERB?
- ERB allows using Ruby and HTML together to create dynamic HTML templates that use variable data from databases.

9. Why do I need a development AND test database?
- Development is where we store our actual data used in the site while the Test database can be used for sample data in tests. By dividing the two, we can write tests with small subsets of data and constantly clear/add data to the tables for testing without polluting our development data.

10. What is CRUD and why is it important?
- CRUD stands for Create, Read, Update, Destory. These are the 4 primary verbs to describe how we interact with data in our application.  It is important to keep our code base simple for other devs to read and understand.

11. What does HTTP stand for?
- Hypertext Transfer Protocol

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

```ruby
<% >
<%= >
```

- <% > allows us to run Ruby code without rendering the return value.  Useful for if/each statements.
- <%= > renders the return value of the Ruby code. Useful for inserting text into the HTML from Ruby.

13. What's an ORM? What does it do?
- ORM stands for object relational mapping.  It is used as a way to interact with your databases without writing raw SQL.  It is useful because the SQL it generates will take into account the type of database system you are using (ie, sqlite vs postgresql) and still work.

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?
- Active Record

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
- CREATE - PUT - create new restaurants
- READ - GET - retrieve information
- UPDATE - PUT/PATCH - revise information
- DESTROY - DELETE - delete information
- Not sure what the other two verbs are

16. What's a migration?
- A migration is a set of instructions for setting up / modifying a database. It includes the columns and data types of each attribute.

17. When you create a migration, does it automatically modify your database?
- No, you must run the migration before it will modify your database.  For Sinatra this has been "rake db:migrate"

18. How does a model relate to a database?
- A model can tell the database if there are associations between tables and also validations for required fields to insert new rows into a table.

19. What is the difference between `#new` and `#create`?
- #new does not automatically save, you have to call #save.  Create automatically saves the new row into the database.

20. Given a table named `animals`, What is the SQL query that will return all info from that table?
    `id     name        number_of_legs
    -----   ------      --------------
      1     panda       4
      2     giraffe     4
      3     whale       0
      4     bird        2
    `
```sql
SELECT * FROM animals
```

21. Using the same table, What is the SQL query that will return only the animals that has 4 legs?
```sql
SELECT * FROM animals WHERE number_of_legs = 4
```

### Review Questions:  
22. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  

- convert the 'films.csv' file into a Ruby CSV object with headers,
- call a .foreach on the object to iterate over each row of the CSV file
- inside the .foreach, call a Film.create() and assign the correspoding attributes with the headers from the CSV file

23. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?

```ruby
activities[:hiking][:supplies] << 'granola bar'
```

24. What are the 4 Principles of OOP? Give a one sentence explanation of each.

- Encapsulation - code should be wrapped into classes with specific responsibilities and accessible only where needed
- Abstraction - expressing intent of methods/variables names so that you can predict behavior without looking at the inner details of the code
- Inheritance - classes can inherit from others, thus sharing their methods to reduce repitiion of code
- Polymorphism - means your code can have many forms, such as methods performing different things depending on the argument

### Self Assessment:
Choose One: (erase the others)
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
