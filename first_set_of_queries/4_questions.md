### 1. List all the actors who acted in at least one film in the 2nd half of the 19th century and at least one film in the 1st half of the 20th century

To find actors who acted in at least one film in the 2nd half of the 19th century (1851-1900) and at least one film in the 1st half of the 20th century (1901-1950), you can use the following SQL query:

We are selecting first name, last name, and ID for all actors who acted in at least one movie between 1851 and 1900.
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
Here is the sample result 
![sample result](./Screenshots/question1)
