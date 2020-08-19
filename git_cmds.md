# Helpful Git commands

## General workflow
```
<make changes>
git stash
git pull
git stash apply
git add <files to add to commit>
git commit -m "<what changed in this commit>"
git push
```

## Don't track specific files or folders
Create a file called .gitignore in the main directory. Here's a common example of contents
```
build/
lib/
__pycache__/
*.pyc
```

## Remove files/folders that you no longer want to track
If a file/folder is added to the .gitignore but was already being tracked, you must explicitly remove it
```
git rm -r --cached <name of file/folder>
```

## Track an empty folder
By default, git doesn't track empty folders. A simple, common way of getting around this is to add an empty file called .gitkeep to the folder.

## Ignore whitespace changes in git diff
```
git diff --ignore-space-at-eol -b -w --ignore-blank-lines
```

## View git diff without file permission changes
```
git diff -G.
```

## Revert previous file permisions
```
git diff -p -R --no-color \
    | grep -E "^(diff|(old|new) mode)" --color=never  \
    | git apply
```
