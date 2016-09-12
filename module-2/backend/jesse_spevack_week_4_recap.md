## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?
###### A cookie is a key-value string object that can be stored on the client's browser. It is one way that we can get around HTTP inability to preserve state.
* What’s the difference between a session and a cookie?
###### Unlike a cookie, a session is encrypted. Session is useful for authorization and authentication.
* What’s a flash and when do you want to use flashes?
###### A flash is another type of key-value that can be stored on the user's browser. Flash is good for alerts.
* Why do people say “HTTP is stateless”?
###### HTTP is stateless because it does not preserve variables from one request to the next.
* What’s authentication? Explain.
###### Authentication is when a user logs in. It's how we know that the user is who they say they are. We used the bcrypt gem to encrypt passwords on a user table in our rails mini project.
* What’s the difference between authentication and authorization?
###### Authentication is how we know who a user is, but authorization is whether or not that user has the ability to access a particular feature. We can handle authorization on a particular view by wrapping an html element in a conditional that checks whether or not an authenticated user should be able to see that particular element. We can also handle authorization more broadly at the page level in the controller by designating entire paths off limits or reserved for particular users.
* What’s a before filter?
###### A before filter is code that runs before each controller method. This is used for authorization.
* How do we keep track of a user once they’ve logged in?
###### We can keep track of a user by storing the user id in the session. This is fairly safe because, again, the session is encrypted.
* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
###### Namespacing a resource is useful for creating a specific path. For example, on my rails mini project, photos were not owned by anyone in the database, but I only wanted an admin to be able to create photos, so I used a namespace to create a admin/photo/new path.
###### Nesting a resource carries meaning that the nested resource belongs to the parent resource or can not be created without being assigned to the parent resource. For example, a comment can't exist without a photo on my rails project.
* At a high level, what tools can you use to implement authorization? How would you use them?
###### We can use Bcrypt to implement authorization. Bcrypt is a gem that handles the hashing of passwords. It is more secure than MD5, which we should not use for passwords.
* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
###### An enum is a way to link an integer value attribute to a symbol. For example, in our rails mini project I used a 1 or 0 value for role to denote admin or default user types. I created an enum which allowed me to call ```user.admin?```
* What are some strategies you can use to keep your views DRY?
###### Layout view - the layout view should contain code that you want to see on every other view, like a navbar and footer.
###### Partials - code that repeats, like a form, can be extracted into a partial.
###### Helper methods - we can also write helper methods like ```logged_in?``` instead of ```!!current_user```
