# Database Architecture: Records and Relationships
In this lesson, we will explore the art of modeling relationships between records in a database. The two primary types of relationships we will focus on are **one-to-many** and **many-to-many**. Keep in mind that choosing between these two often depends on the needs of the application you're building.

Sometimes, what may seem like a clear **one-to-many** relationship could be modeled as **many-to-many**, and vice versa. Naming conventions, particularly for join tables, can also vary and are often subjective.

## What are Associations?
Associations between records define how data relates to one another. Here are some common examples of associations:

- Authors and Books
- Movies and Actors
- Products and Categories
- Teams and Players
- Cities and Neighborhoods
- Courses and Students
- Photographers and Photos
- Bands and Venues
- Parents and Children
- Contractors and Clients
- States and Senators
- Groups and Members

These examples can be modeled as either one-to-many or many-to-many relationships, depending on the requirements of your application.

## **One-to-Many** vs. **Many-to-Many**
To decide which type of relationship is appropriate, ask yourself:

- Can one X have many Y?
- Can one Y have many X?

For example, can one `Course` have many `Students`, and can one `Student` take many `Courses`? This would indicate a **many-to-many** relationship.

Remember, this is more of an art than a science. The right choice often depends on how you plan to use the data in your system.

## Foreign Keys and Join Tables
- For **one-to-many** relationships, the foreign key typically belongs in the table representing the "many" side.
- For many-to-many relationships, you will use a join table to store references to both records.

Naming join tables can also be a subjective process. Choose names that make sense for your application and clearly describe the relationship between the entities. If you can't think of a suitable name, just combine the two table names together.


- How would you model the relationship between Cities and Neighborhoods?
- **one-to-many**
  - Correct! A city can have many neighborhoods, so a **one-to-many** relationship is a good fit.
- **many-to-many**
  - This is possible. Sometimes neighborhood boundaries can overlap, however, I think there is a better fit.
- **many-to-one**
  - Not quite, can you try reversing it?
{: .choose_best #cities_neighborhoods_relationship title="Cities and Neighborhoods" points="1" answer="1" }

- If we model Cities and Neighborhoods as a one-to-many relationship, which table would you add a foreign key to?
- Cities table
  - Not quite! A city can have many neighborhoods, so the foreign key should be in the Neighborhoods table.
- Neighborhoods table
  - Correct! The Neighborhoods table should reference the Cities table.
{: .choose_best #cities_neighborhoods_foreign_key title="Cities and Neighborhoods: foreign key" points="1" answer="2" }

- If we model Cities and Neighborhoods as a one-to-many relationship, what's a good name for the foreign key column?
- `id`
  - Not quite! Usually `id` indicates it's a *primary key*. How can we make this a *foreign key*?
- `city`
  - Not quite!
- `neighborhood`
  - Not quite!
- `city_id`
  - Correct! It's a good practice to reference the table name followed by `id` to indicate it's a foreign key.
{: .choose_best #cities_neighborhoods_foreign_key title="Cities and Neighborhoods: foreign key column name" points="1" answer="4" }

- How would you model the relationship between Authors and Books?
- **one-to-many**
  - Not quite. While an author can write many books, a book can also have multiple authors.
- **many-to-many**
  - Correct! A book can have many authors, and an author can write many books, so a **many-to-many** relationship is a good fit.
- **many-to-one**
  - Not quite, this would indicate that each author can only write one book.
{: .choose_best #authors_books_relationship title="Authors and Books" points="1" answer="2" }

- If we model Authors and Books as a many-to-many relationship, what’s a good name for the join table?
- AuthorBooks
  - Correct! The join table is often named after both tables, such as AuthorBooks.
- BookAuthors
  - Correct! Both AuthorBooks and BookAuthors are valid names for the join table.
- Writings
  - Correct! Writings is a more abstract name, but it can still work for a join table.
{: .choose_all #authors_books_join_table title="Authors and Books: join table" points="1" answer="1,2,3" }

- How would you model the relationship between Movies and Actors?
- **one-to-many**
  - Not quite. One movie can have many actors, but an actor can also appear in many movies.
- **many-to-many**
  - Correct! A movie can have many actors, and an actor can appear in many movies.
- **many-to-one**
  - Not quite. Try reversing the relationship to see if that fits better.
{: .choose_best #movies_actors_relationship title="Movies and Actors" points="1" answer="2" }

- If we model Movies and Actors as a many-to-many relationship, what’s a good name for the join table?
- MovieActors
  - Correct! Movies_Actors is a straightforward name for the join table.
- Casts
  - Correct! Casts is an appropriate name that represents the relationship between movies and actors.
- Actings
  - Correct! Actings can also be used to describe the connection between movies and actors.
- Roles
  - Correct! Roles can also be used to describe the connection between movies and actors.
{: .choose_all #movies_actors_join_table title="Movies and Actors: join table" points="1" answer="1,2,3,4" }

- How would you model the relationship between Products and Categories?
- **one-to-many**
  - Possible, but what if a product can belong to multiple categories and a category can contain multiple products.
- **many-to-many**
  - Correct! A product can belong to multiple categories, and a category can contain many products.
- **many-to-one**
  - Not quite! This would imply each product belongs to only one category.
{: .choose_best #products_categories_relationship title="Products and Categories" points="1" answer="2" }

- If we model Products and Categories as a **many-to-many** relationship, what’s a good name for the join table?
- `ProductCategories`
  - Correct! `ProductCategories` is a typical name for this join table.
- `Classifications`
  - Correct! `Classifications` could be used as a name to describe the connection between products and categories.
- Inventory
  - Not quite! This doesn't describe the relationship between products and categories well.
{: .choose_best #products_categories_join_table title="Products and Categories: join table" points="1" answer="1,2" }

- If we model Teams and Players as a **many-to-many** relationship, what’s a good name for the join table?
- TeamPlayers
  - Correct! Teams_Players is a simple and descriptive name for the join table.
- Rosters
  - Correct! Rosters can represent the collection of players on a team.
- Lineups
  - Correct! Lineups is another valid name to describe the relationship.
{: .choose_all #teams_players_join_table title="Teams and Players: join table" points="1" answer="1,2,3" }

---

- Approximately how long (in minutes) did this lesson take you to complete?
{: .free_text_number #time_taken title="Time taken" points="1" answer="any" }
