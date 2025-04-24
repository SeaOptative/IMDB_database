# IMDB_database
This repository is all about writing queries on a relational movie database. The data in this database is from the [IMDB]( https://www.IMDB.COM/). 

The IMDb (Internet Movie Database) relational dataset is a structured representation of movie-related data designed for querying with SQL. Despite being modeled after the actual IMDb website, it is frequently used as a sample database for studying analytics, data modeling, and SQL. To get this dataset, click [Here](https://developer.imdb.com/non-commercial-datasets/)

I would write certain queries in this repository, such as finding actors and directors using different criteria and counting and ranking films, actors, and directors, among other things. 

- The First set of queries can be found here: [First set of Queries](./first_set_of_quries/4_questions.md)  
- The Second set of queries can be found here: [Second set of Queries](./second_set_of_quries/5_questions.md)


## Tables in the Database
1.	Actor
     -  Contains information about actors.
     -  id, first_name, last_name, gender
2.	Movie
    - Stores basic details about movies.
    - id, name, year, rank
3.	Director
    - Holds information about movie directors.
    - id, first_name, last_name
4.	Cast
    - A many-to-many relationship table showing which actors played in which movies.
    - actor_id, movie_id, role
5.	Movie_director
    - A many-to-many relationship between directors and the movies they directed.
    - director_id, movie_id
6.	Director_genre
    - Holds information about the director and the genre of the movie they directed.
    - director_id, genre, prob
7.	Movie_genre
    - Holds information about movies and the genre they fall into.
    - Movie_id genre
