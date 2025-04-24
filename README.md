# IMDB_database
This repository involves writing queries on a relational movie database. The data in this database is from the [IMDB]( https://www.IMDB.COM/). 

The IMDb (Internet Movie Database) relational dataset is a structured representation of movie-related data designed for querying with SQL. Despite being modeled after the actual IMDb website, it is frequently used as a sample database for studying analytics, data modeling, and SQL. To get this dataset, click [Here](https://developer.imdb.com/non-commercial-datasets/)

I would be writing certain queries in this repository, such as finding actors and directors using different criteria and counting and ranking films, actors, and directors, among other things. 

## Tables in the Database
1.	Actor
o	Contains information about actors.
o	id, first_name, last_name, gender
2.	Movie
o	Stores basic details about movies.
o	id, name, year, rank
3.	Director
o	Holds information about movie directors.
o	id, first_name, last_name
4.	Cast
o	A many-to-many relationship table showing which actors played in which movies.
o	actor_id, movie_id, role
5.	Movie_director
o	A many-to-many relationship between directors and the movies they directed.
o	director_id, movie_id
6.	Director_genre
o	Holds information about director and the genre of the movie they directed.
o	director_id, genre, prob
7.	Movie_genre
o	Holds information movies and the genre they fall into.
o	Movie_id genre
