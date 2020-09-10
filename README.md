# Recipe Book

## Topics

- database modeling.
- migration scripts.
- seeding.
- knex.

## Assignment

Design the **data model** for a _recipe book_ application, then use `Knex migrations and seeding` functionality to build a `SQLite3` database based on the model and seed it with test data.

The requirements for the system, as stated by the client are:

- have a way to manage recipes.
- have a way to manage ingredients.
- a **recipe** could have more than one **ingredient** and the same **ingredient** can be used in multiple recipes. Examples are _"cup of corn flour"_ or _"gram of butter"_.
- when saving the ingredients for a **recipe** capture the quantity required for that **ingredient** as a floating number.
- have a way to save step by step instructions for preparing a recipe.

**Hint**: Before writing any code, write out all desired tables in the data model and determine all relationships between tables. 

### Migrations and Seeds

- Write a migration file that creates all tables necessary to model this data
- Write seed files to populate the tables with test data. **Hint**: Keep your recipes *very* simple or this step could become extremely time consuming.

### Data Access

In addition to the `migrations` and `seeding` scripts, write a data access file that **exports** an object with the following functions:

- `getRecipes()`: should return a list of all recipes in the database.
- `getShoppingList(recipe_id)`: should return a list of all ingredients and quantities for a given recipe
- `getInstructions(recipe_id)`: should return a list of step by step instructions for preparing a recipe

Organize and name your files anyway you see fit.

## Stretch Problem

Build the following endpoints. Write any additional data access helpers as needed.

- `GET /api/recipes/`: all recipes (without details about ingredients or steps)
- `GET /api/recipes/:id/shoppingList`: a list of ingredients and quantites for a single recipe
- `GET /api/recipes/:id/instructions`: a correctly ordered list of how to prepare a single recipe
- `GET /api/ingredients/:id/recipes`: all recipes in the system that utilize a single ingredient 

## Tips

## Components
    - entities -> resources -> nouns -> tables
    - properties -> columns
    - relationships -> sub-routes -> foreign keys

## Workflow
    - identify entities
    - identify relationships
    - identify properties

## Relationships
    - one to one: rare
    - one to many -> this is the one
    - many to many -> a trick

## Mantras

    - every table must have a primary key
    - work on two or three entities at a time (map to the relationships below)
    - one to many relationships -> requires a foreign key
        - the foreign key goes on the many side
    - many to many -> make a third table
    - the third table can and probably will have extra information