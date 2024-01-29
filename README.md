# Express + SQL + Vanilla JS project

- [Express + SQL + Vanilla JS project](#express--sql--vanilla-js-project)
- [Welcome!](#welcome)
- [Overview](#overview)
  - [Users?](#users)
  - [More Challenge](#more-challenge)
- [Example Ideas](#example-ideas)
- [Timeline](#timeline)
- [Tech Checklist](#tech-checklist)
  - [Database - Migrations/Seeds](#database---migrationsseeds)
  - [Database - Models](#database---models)
  - [Database - ERD](#database---erd)
  - [JSON API](#json-api)
  - [Client Side](#client-side)
  - [Client Side A11y](#client-side-a11y)

# Welcome!
We're almost done with Express, so it's time to make sure you all know the fundamentals! This is going to feel like a lot, but remember: take one thing at a time. Every complex idea is just a bunch of smaller ideas standing on each other's shoulders in a trench coat.

You'll be building your own migrations, seeds, models, routes, controllers, and client side code. We know there is *always* the temptation to go crazy on the frontend and build cool looking things, but try to resist! We're looking at your ability to lay sturdy foundations right now, the sky scrapers will come later.

# Overview
You're going to be building a simple app that has 2 database tables with a `has many/belongs to` relationship. You'll setup the required knex files to create 2 migration and a seed file. You'll also of course need two JS models for your tables.

You'll also need to create a JSON API that has all the routes you need to have full CRUD on *both* resources. The challenge here is that your relationships need to be reflected in these routes. Check the checklist below to see what we mean.

Finally, you'll need to create a client side app that can talk to your API and display the data and allow users to interact with it. For now, your app should be a single page with modals or re-renders to display information.

## Users?
Not this time! We'll deal with authentication and users in the next Express project. Adding users is of course crucial! But to do it right, we'll need to learn a few tricks we haven't seen yet. Before we add all that complexity, we want to make sure that you know how to do the basics.

That means that this app, even though it would be public and available to anyone, is just already for you. So any post that exists, it's assumed it's just for you.

## More Challenge
Instead of users, if you're looking for more challenges, then add more tables to your DB. We're only asking for a `has many/belongs to` relationship, but it would be great if you could do a `many to many` relationship.


# Example Ideas
Here are a bunch of ideas that don't have users and only need a `has many/belongs to` relationship.

- An doctor appointment tracker (doctors and appointments)
- A recipe app that lets you leave notes of the recipe each time you make it (recipes and notes)
- A movie app that lets you review movies (movies and reviews)
- A finance tracker that lets you track your spending (categories and transactions)
- A to do list app that you can tag rewards to when you complete certain tasks (tasks and rewards)

And those are just the `has many/belongs to` examples. You can model more complex relationships if you add in a join table. But only do this if you feel comfortable with everything you've already learned about the nuts and bolts of Express and SQL.

# Timeline
We're going to give you a vague timeline as we hope by now you're becoming more self sufficient with planning.

- **Day 0:** You just had the kickoff, and can see all the requirements. This time is up to you to research the aspects of this project that are the most confusing for you. Definitely be ready to go for the next day with what your project *will* be.
- **Day 1:** Your ERD diagram is complete, and you are able to run both of your migrations
- **Day 2:** Your models are created and you can seed your database. Your hosting your empty frontend code.
- **Day 3:** Your API is complete and you can make requests to it from the client.
  - This is our MVP! Your backend is pretty much complete and you can see something on the frontend
- **Day 4:** You can read both of your resources fully, and on one of them you have full CRUD capabilities
- **Day 5:** Your app is now rendering a polished looking, it is fully accessible as well.
- **Weekend:** Polish and bug squashing! You should also focus on your presentation
- **Final Day:** Presentations and science fair, you did it!

# Tech Checklist
Use this as a guideline to make sure you know how to do all the essential skills of this module. Remember, the client is not the focus, this project is *specifically* focused on your ability to:
- interact with a database through migrations, seeds, and models
- Host a RESTful API
- Host static assets on a server (ie, your client code)

## Database - Migrations/Seeds
- [ ] The `knexfile.js` is set up correctly
- [ ] You wrote a migration for the parent relationship
- [ ] You wrote a migration for the child relationship
- [ ] Every migration has an up and down function
- [ ] Every table has an incrementing ID column
- [ ] Every table has at least 2 properties on the model (not include keys)
- [ ] The has many/belongs to relationship is set up correctly between the two tables
- [ ] There is a seed file that destroys all the data in the database and recreates a default data set
- [ ] The seed file uses your models to create the data
- [ ] There is an npm script you can run to migrate your database
- [ ] There is an npm script you can run to rollback your database
- [ ] There is an npm script to seed your db
  - All these scripts are just going to essentially be aliases for `knex` commands, that's ok!


## Database - Models
- [ ] There is a model for the parent
- [ ] There is a model for the child
- [ ] Models are each in their own file

The parent model can:
- [ ] create a new parent resource
- [ ] get all parents
- [ ] get a single parent
- [ ] update a parent
- [ ] delete a parent
- [ ] get all the children for a specific parent

The child model can:
- [ ] create a new child resource
- [ ] get all children resources
- [ ] get a single child
- [ ] update a child
- [ ] delete a child
- [ ] The child model is able to get the single parent for a specific child

## Database - ERD
- [ ] Every table is included in the ERD diagram
- [ ] All properties and their data types are clearly labeled on each table
- [ ] The relationship between the two tables is correct
  - Essentially the crows feet are pointing in the right direction

## JSON API
Regardless of whether or not you actually *need* all of these routes on your frontend, these routes must exist on your API. We're making sure that you will be able to handle more complex APIs later on.

There is a route to:
- [ ] create a new parent
- [ ] get all parents *and* their children
  - For example, when you fetch your list of articles, the associated comments are in a nested array
  - For an extra challenge, determine if children should be included in the response with a query param!
- [ ] get a single parent
- [ ] update a parent
- [ ] delete a parent
- [ ] create a new child
- [ ] get all children
- [ ] get a single child
- [ ] update a child
- [ ] delete a child
- [ ] get all children for a parent
- [ ] **get a *specific* parent's children**

\* You do not need to include the parent resource when fetching the individual child, that's totally up to you if it makes sense for your design.

These hold for any applicable routes:
- [ ] The api routes are behind `/api`
- [ ] All routes uses proper REST naming conventions
- [ ] Whenever a `body` is sent to the server, the data is verified to be correct
- [ ] Whenever a `body` is sent to the server, if the data is not correct it is handled
  - At minimum, the right status code is sent and the server does not crash

The following codes are used and *only* in the correct circumstances:
- [ ] 201
- [ ] 204
- [ ] 400
- [ ] 404
- [ ] 500

## Client Side
The client really isn't the focus of this project, the whole goal is that you have a frontend that can properly communicate with the backend. How you want to display the data is largely up to you, modals would be a really good option here. Remember, in our *very next* project we'll learn about "Client Side Routing" but for now, just keep everything on one page.

- [ ] The project uses Vite
- [ ] The *built* client side code is hosted by the server
- [ ] The Vite dev server proxies to the JSON server
- [ ] The client is able to make `fetches` to the server
- [ ] The submitting form's default behavior is prevented
- [ ] Whenever child information is displayed, it is clearly associated with the parent
  - Either literally showing through text, or in the visual hierarchy so they are all contained within a list that is in the parent's information container
- [ ] For database entity creation, pessimistic rendering was always used
  - That won't always be true with all your projects, we're just making sure you can do it

The client is able to:
- [ ] display all the parent information
  - The rendering choices are open ended, but a user should be able to see all the information about all parents *somehow*
- [ ] create a new parent
- [ ] update a parent
- [ ] delete a parent
- [ ] display all the child information
  - Just like the parent, this is open ended but must still be true
- [ ] create a new child
- [ ] update a child
- [ ] delete a child

## Client Side A11y
- [ ] There is a `main` element
- [ ] At least one `h1` element on the page
- [ ] At least one `section` is used properly
  - You know how to make a `section` a proper landmark, right?
- [ ] Heading tag hierarchy is always correct
- [ ] `div` is never used in place of `ul` and `li`
- [ ] Every `form` `input` has a proper `label`
- [ ] Each `form` is `aria` labelled properly to make it a landmark
- [ ] Every `img` has a unique `alt` (if applicable, get points if no image)
- [ ] All colors have a AAA difference
  - https://color.a11y.com can check your site for you!
- [ ] All buttons look like buttons, all links look like links
  - Buttons have some kind of a visual box and links are underlined and different colors
