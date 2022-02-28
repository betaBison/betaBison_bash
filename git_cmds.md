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

## New branch
```
git checkout -b your-name/name-of-your-bugfix-or-feature
git stash
git pull
git stash apply
git add <files to add to commit>
git commit -m "<describe changes in this commit>"
git push origin your-name/name-of-your-bugfix-or-feature
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

## Add submodule
```
git submodule add -b <branch> <ssh-url-for-cloning> <path-to-place-save-including-repo-name>
# e.g. git submodule add -b android-functionality git@github.com:Stanford-NavLab/gnss_lib_py.git lib/gnss_lib_py
git submodule update --remote
```

## Remove submodule
```
git submodule deinit <path_to_submodule>
git rm <path_to_submodule>
git commit-m "Removed submodule "
rm -rf .git/modules/<path_to_submodule>
```
