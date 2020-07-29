---
---
## Working with repositories that contain submodules

### Cloning a repository that contains submodules

If you want to clone a repository including its submodules you can use the --recursive parameter.

```sh
git clone --recursive [URL to Git repo]
```

If you already have cloned a repository and now want to load it’s submodules you have to use submodule update.

```sh
git submodule update --init
# if there are nested submodules:
git submodule update --init --recursive
```

### Downloading multiple submodules at once

```sh
# download up to 8 submodules at once
git submodule update --init --recursive --jobs 8
git clone --recursive --jobs 8 [URL to Git repo]
# short version
git submodule update --init --recursive -j 8

# pull all changes in the repo including changes in the submodules
git pull --recurse-submodules

# pull all changes for the submodules
git submodule update --remote
```

Executing a command on every submodule

```sh
git submodule foreach 'git reset --hard'
# including nested submodules
git submodule foreach --recursive 'git reset --hard'
```

## Creating repositories with submodules

```sh
# add submodule and define the master branch as the one you want to track
git submodule add -b master [URL to Git repo] 
git submodule init
```

Updating which commit your are tracking

```sh
# update submodule in the master branch
# skip this if you use --recurse-submodules
# and have the master branch checked out
cd [submodule directory]
git checkout master
git pull

# commit the change in main repo
# to use the latest commit in master of the submodule
cd ..
git add [submodule directory]
git commit -m "move submodule to latest commit in master"

# share your changes
git push
```

## delete

```sh
git submodule deinit -f — mymodule

rm -rf .git/modules/mymodule

git rm -f mymodule
```