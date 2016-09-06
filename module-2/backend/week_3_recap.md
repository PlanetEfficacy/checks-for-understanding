## Week Three Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What are the 3 main features in an ERD?

```
An entity relationship diagram has entities (nouns). Entities can be either concrete objects, organizations, or abstract objects. Entities have many instances. The next part of an ERD is the relationship, which is the interactions between or among entities. The final piece of an ERD is the cardinality of a relationship. There are three types of cardinalities: one to many, one to one, and many to many.
```
2. Create an ERD for the following database: Restaurants, Customers, Items, Ingredients, Beverages, Orders, Vendors.

```
restaurants serve customers (have many)
restaurants sell items (have many)
Items contain ingredients (have many)
restaurants sell beverages (have many)
customers place orders (have many)
restaurants buy from vendors (have many)```

3. What is the entry at the command line to create a new rails app?

```rails new <app name>```

4. What do Models generally inherit from in rails?

```
Models inherit from ActiveRecord::Base```

5. What do Controllers generally inherit from in a rails project?

```
Controllers inherit from ApplicationController```

6. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

```
resources :horse, only: [:show]```

7. What rake task is useful when looking at routes, and what information does it give you?

```rake routes```

8. What is an example of a route helper? When would you use them?

```
An example of a route helper is horse_path. I would use a route helper when creating a link in a view or redirecting to a particular page in my controller.
```

9. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

```
url provides the entire URI starting with http.... path provides the relative path from the root url.
```
10. What are strong params and why are the necessary?

```
Strong params limit the attributes of an object that can be modified by a submitted form. To do so, attributes must be white listed in a private controller method. These are important because they add a layer of security that prevent unexpected database manipulations.

```
11. What role does `form_for` play in helping us create our forms?
```
form_for tells the app which model the form is meant for.
```
12. How does `form_for` know where to submit the user's input?
```
By convention the form_for submission with go to the model's controller.
```
13. Create a form using a `form_for` helper to create a new `Horse`.

``` <%= form_for(@horse) do |f| %>
      <%= f.label :name %>
      <%= f.text_field :name %>
      <%= f.submit %>
    <% end %>
```
14. Why do we want to validate our models?

```
We validate our models because we want to make sure that data in the database is clean e.g. has all the expected attributes.
