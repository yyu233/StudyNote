A CASE statement allows us to create different outputs (usually in the SELECT statement). It is SQL’s way of handling if-then logic.

```
SELECT name,
CASE
WHEN genre = 'romance' or genre = 'comedy' THEN 'Chill'
ELSE 'Intense'
END AS 'Mood'
FROM movies;
```
