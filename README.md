## Sample input of IntelliMerge for quick start 

A sample repository as the input of IntelliMerge for quick start, see https://github.com/Symbolk/IntelliMerge for more details.

Forked from: https://github.com/tobyweston/Refactoring-Chapter-1, modified to demonstrate how IntelliMerge works.

This repository includes Java code following along with the first chapter of Martin Fowler's book: _Refactoring: Improving the Design of Existing Code_.

### Branches and Changes

- ours
```bash
* 4d540f2 - (HEAD -> ours, github/ours) [refactor] Rename director to mainDirector, since one movie could have more than one directors. () <Symbolk>
* 43bc21c - [edit] Make Method getFrequentRenterPoints public. () <Symbolk>
```
- theirs

```bash
* 2e38226 - (HEAD -> theirs, github/theirs) [refactor] Extract Method getDirector() and setDirector() from categorized movies to parent Movie class. () <Symbolk>
* 9026b4e - [refactor] Rename Method getFrequentRenterPoints() to getPointsOfFrequentRenters(). () <Symbolk>
```

- oursMergedtheirs

```shell
* 5fcd7e3 - (HEAD -> oursMergedtheirs, github/oursMergedtheirs) [fix] Fix incorrect auto-merged code by git. (5 minutes ago) <Symbolk>
*   a41d00b - [merge] Merge theirs to ours manually. (6 minutes ago) <Symbolk>
|\
| * 2e38226 - (github/theirs, theirs) [refactor] Extract Method getDirector() and setDirector() from categorized movies to parent Movie class. (47 minutes ago) <Symbolk>
| * 9026b4e - [refactor] Rename Method getFrequentRenterPoints() to getPointsOfFrequentRenters(). (50 minutes ago) <Symbolk>
* | 4d540f2 - (github/ours, ours) [refactor] Rename director to mainDirector, since one movie could have more than one directors. (44 minutes ago) <Symbolk>
* | 43bc21c - [edit] Make Method getFrequentRenterPoints public. (45 minutes ago) <Symbolk>
|/
* b5fbc82 - (github/master, master) Add two sub class movies. (54 minutes ago) <Symbolk>

```

### Merge Branches

Run the following commands to merge `theirs` branch into `ours`:
```shell
git checkout theirs
git checkout ours
git merge theirs
```

Lots of conflicts will be reported, since both side performed refactoring changes:

```shell
$ git merge theirs
Auto-merging src/main/java/bad/robot/refactoring/chapter1/Price.java
CONFLICT (content): Merge conflict in src/main/java/bad/robot/refactoring/chapter1/Price.java
Auto-merging src/main/java/bad/robot/refactoring/chapter1/NewReleasePrice.java
CONFLICT (content): Merge conflict in src/main/java/bad/robot/refactoring/chapter1/NewReleasePrice.java
Auto-merging src/main/java/bad/robot/refactoring/chapter1/HorrorMovie.java
CONFLICT (content): Merge conflict in src/main/java/bad/robot/refactoring/chapter1/HorrorMovie.java
Auto-merging src/main/java/bad/robot/refactoring/chapter1/ComedyMovie.java
CONFLICT (content): Merge conflict in src/main/java/bad/robot/refactoring/chapter1/ComedyMovie.java
Automatic merge failed; fix conflicts and then commit the result.

/f/workspace/dev/intellimerge-sample-input (ours|MERGING)
$ git s
On branch ours
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:

        modified:   src/main/java/bad/robot/refactoring/chapter1/Movie.java

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   src/main/java/bad/robot/refactoring/chapter1/ComedyMovie.java
        both modified:   src/main/java/bad/robot/refactoring/chapter1/HorrorMovie.java
        both modified:   src/main/java/bad/robot/refactoring/chapter1/NewReleasePrice.java
        both modified:   src/main/java/bad/robot/refactoring/chapter1/Price.java

```