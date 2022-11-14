---
course: CPSC304
title: Student SQL Exercises
topic: Exercises
tags:
module: 6
date: [[2022-10-25]]
---

## Table Definitions
1. Movie(MovieID, Title, Year)
2. StarsIn(MovieID, StarID, Character)
3. MovieStar(StarID, Name, Gender)

Find female movie stars
```SQL
SELECT *
FROM MovieStar
WHERE Gender = 'female'
```

What are the names of female movie stars?
```SQL
SELECT name
FROM MovieStar
WHERE Gender = 'female'
```

What are the titles of movies from prior to 1939
```SQL
SELECT title
FROM Movie
WHERE Year < 1939
```

Find the person names and character names of those who have been in movies
```SQL
SELECT StarsIn.Character, MovieStar.Name
FROM StarsIn s, MovieStar m
WHERE s.StarID = m.StarID
```

$\pi_{Name, Character}(MovieStar \Join StarsIn)$

Find the names of all movie stars who have been in a movie (note: rows can be duplicated)
```SQL
SELECT DISTINCT Name
FROM StarsIn S, MovieStar M
WHERE S.starID = M.StarID
```

## Clickers
Be careful when selecting from multiple relations. E.g., [[M6 Clicker 1]]

Find IDs of MovieStars who've bee in a movie in 1944 or 1974
```SQL
SELECT StarID -- different from the union solution if no DISTINCT
FROM StarsIn S, Movie M
WHERE S.MovieID = M.MovieID AND (M.Year = 1944 OR M.Year = 1974)

-- Set union solution:
SELECT StarID
FROM StarsIn S, Movie M
WHERE S.MovieID = M.MovieID AND M.Year = 1944
UNION
SELECT StarID
FROM StarsIn si, Movie m
WHERE S.MovieID = M.MovieID AND M.Year = 1974
```

Find IDs of stars who have been in a movie in 1944 and 1974
```SQL
SELECT DISTINCT StarID
FROM StarsIn S1, Movie M1, StarsIn S2, Movie M2
WHERE S1.StarID = S2.StarID AND
    S1.MovieID = M1.MovieID AND S2.MovieID = M2.MovieID AND
    M1.Year = 1944 AND M2.Year = 1974

-- Intersect Solution
SELECT DISTINCT StarID
FROM StarsIn S, Movie M
WHERE S.MovieID = M.MovieID AND M.Year = 1944
INTERSECT
SELECT DISTINCT StarID
FROM StarsIn S, Movie M
WHERE S.MovieID = M.MovieID AND M.Year = 1974

-- Nested query solution
SELECT DISTINCT StarID
FROM StarsIn S, Movie M
WHERE S.MovieID = M.MovieID AND M.Year = 1944 AND
      S.StarID IN (SELECT StarID
                   FROM StarsIn S2, Movie M2
                   WHERE S2.MovieID = M2.MovieID AND M2.Year = 1974)
```

Find ids and names of female stars who have been in a movie with ID 28
```SQL
SELECT StarID, Name
FROM MovieStar MS, StarsIn S
WHERE MS.StarID = S.StarId AND MS.Gender = 'female' AND S.MovieID = 28

-- Female stars who have not been a movie with ID 28
SELECT StarID, Name
FROM MovieStar
EXCEPT
SELECT StarID, Name
FROM MovieStar MS, StarsIn S
WHERE MS.StarID = S.StarId AND MS.Gender = 'female' AND S.MovieID = 28
```

Find movies made after "Fargo"
```SQL
SELECT MovieID
FROM Movie M
WHERE M.Year > ANY (SELECT Year
                    FROM Movie M2
                    WHERE M2.Title = "Fargo")
                    
SELECT MovieID
FROM Movie M
WHERE EXISTS (SELECT *
              FROM Movie M2
              WHERE M2.Title = "Fargo" AND M.Year > M2.Year)
```