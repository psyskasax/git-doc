## Merge
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

