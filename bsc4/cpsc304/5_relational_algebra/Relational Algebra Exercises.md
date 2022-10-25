![[Pasted image 20221018163243.png|600]]

1. Find names of actors who have been in "Indiana Jones"
$\pi_{Name}(\sigma_{Title = ``Indiana Jones''}(Movie) \Join StarsIn \Join MovieStar)$

2. Find the names of actors who have been in "Indiana Jones" and "Star Wars"
$Indy \leftarrow \pi_{starID}(\sigma_{Title = ``Indiana Jones''}(Movie) \Join StarsIn)$
$StarWars \leftarrow \pi_{starID}(\sigma_{Title = ``Star Wars''}(Movie) \Join StarsIn)$
$CoolPeople \leftarrow Indy \cap StarWars$
$\pi_{name}(CoolPeople \Join MovieStar)$

3. Find the names of actors who have been in a movie with the same title as the actor's name

4. Find the name of actors who have been in all movies
$InAll \leftarrow \pi_{StarID, MovieID}(StarsIn / \pi_{MovieID}(Movie)$
$\pi_{Name}(InAll \Join MovieStar)$

5. Find names of actors who have been in all movies after 1950
$InAll \leftarrow \pi_{StarID, MovieID}(StarsIn / \pi_{MovieID}(\sigma_{Year > 1950}(Movie))$
$\pi_{Name}(InAll \Join MovieStar)$

