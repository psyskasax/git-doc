## Stash  

Stasher
`git stash save "message de stash"`  

Voir la liste des stash  
`git stash list`  

	stash@{0}: On main: add style to our site
	stash@{1}: WIP on main: 5002d47 our new homepage
	stash@{2}: WIP on main: 5002d47 our new homepage

Appliquer le stash mais le conserver dans la liste  
`git stash apply ['stash@{2}']`  
Par défaut le dernier stash est appliqué si rien de précisé (stash@{2})  

Appliquer le stash et le supprimer de la liste  
`git stash pop 'stash@{2}'`  
