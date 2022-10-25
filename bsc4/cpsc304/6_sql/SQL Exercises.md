---
course: CPSC304
title: SQL Exercises
topic:
tags:
module: 6
date: [[2022-10-25]]
---

- Find female movie stars
```SQL
SELECT *
FROM MovieStar
WHERE Gender = 'female'
```

- What are the names of female movie stars?
```SQL
SELECT name
FROM MovieStar
WHERE Gender = 'female'
```

- What are the titles of movies from prior to 1939
```SQL
SELECT title
FROM Movie
WHERE Year < 1939
```

- Find the person names and character names of those who have been in movies
```SQL
SELECT StarsIn.Character, MovieStar.Name
FROM StarsIn s, MovieStar m
WHERE s.StarID = m.StarID
```

$\pi_{Name, Character}(MovieStar \Join StarsIn)$

- Find the names of all movie stars who have been in a movie (note: rows can be duplicated)
```SQL
SELECT DISTINCT Name
FROM StarsIn S, MovieStar M
WHERE S.starID = M.StarID
```

## Clickers
Be careful when selecting from multiple relations. E.g., [[M6 Clicker 1]]
