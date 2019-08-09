# Ruby on Rails - Ruby & Ruby on Rails Basics - Introduction to Ruby on Rails - Project

## Step One - Generate Rails App

1. Create a new rails app using the rails app generator
2. Scaffold the resources shown below using rails generators

*Note: Don't forget to initialize and setup the database as part of your scaffolding process.*

**`User`**

| attribute  | type     |
| ---------- | -------- |
| id         | integer  |
| email      | string   |
| active     | boolean  |
| created_at | datetime |
| updated_at | datetime |

**`Task`**

| attribute    | type     |
| ------------ | -------- |
| id           | integer  |
| name         | string   |
| priority     | integer  |
| completed_at | datetime |
| created_at   | datetime |
| updated_at   | datetime |

## Step Two - Explain Rails MVC

Write all of your answers to the questions below in a separate readme named SOLUTIONS.md.

### Rails MVC

First, start the rails server. Then, make a request to `/tasks/new`, fill out the form and submit it in order to create a new task.

1. What controller and action handles the data from the form submission?
2. What controller and action would be used if you did a `GET` request on the `/users` route?
3. Write out the step-by-step process that your rails application will take to render the `tasks/new` route.
4. What file is responsible for managing the mapping between your application and the `tasks` database table?

### Rails RESTful Actions

5. Explain all 7 of the RESTful actions in Rails

   - List each action by its name
   - Explain which HTTP verbs pair with each action
   - Write a short sentence for each action that summarizes what it does

## Step Three - Modify Routes

Our application has all 7 actions available for both Users and Tasks. We don't want that--we want to set limits on these resources.

  - Limit users resource to *only* allow `index` and `show`
  - Limit tasks resource to allow everything *except* `destroy`
  - remove the corresponding controller actions that are no longer routable

## Step Four - Use Rails Console to Create a User

We removed the routes to create a User because we only want developers to be able to do that. The way our developers will create new users for this app is to use the rails console. Use the rails console to create 2 users. Paste the commands you used into the `SOLUTIONS.md` file.
