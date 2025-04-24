### 1. List all the actors who acted in at least one movie in the 2nd half of the 19th century and at least one movie in the 1st half of the 20th century

To find actors who acted in at least one movie in the 2nd half of the 19th century (1851-1900) and at least one movie in the 1st half of the 20th century (1901-1950), you can use the following SQL query:

-We are selecting first name, last name, and ID for all actors who acted in at least one movie between 1851 and 1900.
```

SELECT
    a.first_name AS "First name", 
    a.last_name AS "last name", 
    a.id AS "ID"
FROM actor a

--this section joins the actor,cast and movie tables to find the actors and the movies they acted in. 
JOIN cast c ON a.id = c.actor_id
JOIN movie m ON c.movie_id = m.id
  WHERE m.year BETWEEN 1851 AND 1900

INTERSECT
--INTERSECT makes sure that we only get actors who appear in both time periods (1851 - 1900 and 1901 - 1950).

SELECT
    a.first_name AS "First name", 
    a.last_name AS "last name", 
    a.id AS "ID"
FROM actor a 

JOIN cast c ON a.id = c.actor_id
JOIN movie m ON c.movie_id = m.id
WHERE m.year BETWEEN 1901 AND 1950;
```
Here is the sample result showing the first name, last name, and ID of all actors who acted in at least one movie in the 2nd half of the 19th century and at least one movie in the 1st half of the 20th century.

![sample result](./screenshots/question1.png)



### 2. List all the directors who directed a movie in a leap year 

-To list all the directors who directed at least one movie in a leap year, you can use the following SQL query:

```
SELECT DISTINCT --the DISTINCT function ensures that each director only show up once, even if they directed multiple movie in leap years.
    d.id AS "Director ID", 
    d.first_name AS "First name", 
    d.last_name AS "Last name"
FROM director d

--join the director, movie_director, and movie tables to find all directors of movies released in leap years.
JOIN movie_director md ON d.id = md.director_id
JOIN movie m ON md.movie_id = m.id

WHERE 
--A leap year occurs if the year is divisible by 400 or divisible  by 4 AND not divisible by 100.
	(m.year % 400 = 0) OR (m.year % 4 = 0 AND m.year % 100 != 0);

```
Here is the sample result showing the first name, last name, and ID of all directors who directed at least one movie in a leap year.
![sample result](./screenshots/question2.png)
