## Rebase

### Basic rebasing on personnal branch

A comparer avec [Merge](./merge.md)

Avant rebase :  
| main | branch a |
|-|-|
| commit 0 fd22594e | commit 0 fd22594e |
| commit 1 9a3cd5ee | commit 3 f1c7b742 |
| commit 2 bd036d4c | commit 4 37ff98cd |

Depuis branch a : `git rebase main`  
| main | branch a |
|-|-|
| commit 0 fd22594e | commit 0 fd22594e |
| commit 1 9a3cd5ee | commit 1 9a3cd5ee |
| commit 2 bd036d4c | commit 2 bd036d4c |
| - | commit 3 **bb61dab0** |
| - | commit 4 **80646d9b**|

> Les 2 branches ont différé après le commit 0. Les 2 commits de main sont appliqués sur le commit 0 de la branch a, puis les 2 commits de la branch a sont ré-appliqués en changeant de numéro de commit (nouveaux commits)  

> /!\ Ne pas faire l'inverse, c'est à dire rebaser main à partir de branch a, car cela modifie les commits sur main 