## Merge

A comparer avec [Rebase](./rebase.md)

Avant merge :  
| main | branch b |
|-|-|
| commit 0 fd22594e | commit 0 fd22594e |
| commit 1 9a3cd5ee | commit 5 0b6fb22e |
| commit 2 bd036d4c | commit 6 bf53ef31 |

Depuis branch a : `git merge main`  
| main | branch b |
|-|-|
| commit 0 fd22594e | commit 0 fd22594e |
| commit 1 9a3cd5ee | commit 1 9a3cd5ee |
| commit 2 bd036d4c | commit 2 bd036d4c |
| - | commit 5 0b6fb22e |
| - | commit 6 bf53ef31 |
| - | **merge commit 276906a0** |

### Merger test/001 sur test/002 sans commiter sur test/002

| commit | main | test/001 | test/002 |
|-|----------|--------------|------------|
|1| initial commit | - | - |
|1| `checkout -b test/001` | - | - |
|1| `checkout -b test/002` | - | - |
|1*| - | `mkdir tests` | - |
|1*| - | `touch tests/test_001.txt` | - |
|1*| - | `git add .` | - |
|2| - | `git commit -m "new folder and new file` | - |
|1*| - | - | `git merge --no-commit --no-ff test/001` |
|1*| - | - | branch is in status "**\|MERGING**" |
|1| - | - | `git reset --hard HEAD` |

