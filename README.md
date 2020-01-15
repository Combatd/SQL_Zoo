# SQL Zoo

## Learning Goals

* Be able to write simple SQL queries using the SELECT, FROM, and WHERE clauses
* Be able to write complicated queries using JOIN and subqueries
* Be able to use GROUP BY with aggregate functions
* Be able to use the various types of JOIN
* Be able to write queries with self-joins

## Getting Started
* Ensure the PostgreSQL app is running on your machine (you should see an elephant in the menu bar)
* Navigate to the directory and run the following:
```
bundle install
./import_db.sh
```
* Run all specs for a section
```
bundle exec rspec spec/01_select_basics_spec.rb
```
* Run a example by appending line number
```
bundle exec rspec spec/01_select_basics_spec.rb:42
```

## Notes on Tables
Some of the exercises involve joining tables together, and the purpose of some columns may not be clear from the name alone. The aim of this section is to clarify the structure of these tables.

### First Joins (movie tables)
* castings is a join table that links movies to actors.
    * castings.actor_id is a foreign key pointing to an id in the      actors table
    * castings.movie_id is a foreign_key pointing to an id in the movies table
    * ord represents the position of the actor for the casting. The lead actor will have an ord of 1, with higher numbers representing less important roles.

* movies.director_id is a foreign key that points to an id in the actors table.

### More Joins (music tables)
* albums.asin is the primary key for the albums table. Each album has a unique asin. (asin stands for "Amazon Standard Item Number.")
* tracks.album and styles.album are foreign keys that point back to albums.asin.
* tracks.song represents the name of a track.

### Self Joins (bus tables)
* routes.num is, deceptively, not an integer or a float. Rather, it is a string that represents the "line number" of the route (i.e., the "32A" bus).
* routes.pos represents the position of a stop along the given line (num).
* routes.stop_id is a foreign key that points to an id in the stops table.