## Git/GitHub

**Configuring Git**
```
git config --global user.name "Your Name"
git config --global user.email youremail@provider.com
```

**Adding Git version control to a project folder:**
```
git init
```
Git creats a ```.git``` folder in this directory where the history of the project is stored. This is a hidden folder indicated by the ```.``` in the name. This ```.git``` folder also tells Git that you are working in a repository.

**Check current state of the repository:**
```
git status
```
This tells us the status of the repository. 

```
$ git status
# On branch master
#
# Initial commit
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#       README.md
#
nothing added to commit but untracked files present (use "git add" to track)
```
+ It is telling us that we are working on the master branch. A single repository can have multiple branches, each containing a different version of the code. It's common to use master as the stable branch, which contains production-ready code (the code powering your actual, live product), and a development branch which is used as you develop new features (code not shipped to users until it's ready).
+ It is also telling us the **status** of the files. Example above is telling us there are untracked files, which are files which are inside the repo, but they are not being tracked by version control.

**Tell git to start tracking the file:**
```
$ git add README.md
```
After doing this and then running ```git status``` you should see:
```
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   README.md
```

**Commit the file to the history:**
```
$ git commit -m "Initial commit"
```

After doing this, you should see:
```
$ git commit -m "Initial commit"
[master (root-commit) f9ba0e4] Initial commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
```

After doing this and then running ```git status``` you should see:
```
$ git status
# On branch master
nothing to commit, working directory clean
```
This means all of your recent work was commited.

### Cheatsheet

**How to commit your work for the first time in a new project:**

+ Initialize a repository: type ```git init```. Command line should say ```Initialized empty Git repository```
+ Check the repository: type ```git status```. It should show you the untracked files.
+ Save your progress: track the file by adding it using ```git add`` followed by each of the filenames, one at a time.
+ Check what has changed: type ```git status```.
+ Commit the changes: type ```git commit -m "commit message"```
+ Success! If you type ```git status``` You should see ```Nothing to commit, working directory clean"```

**Pushing your snapshot to GitHub:**

+ Go to github.com and create a new repository
+ Add GitHub repository as a remote branch: Use ```git remote add origin git@github.com...``` (follow GitHub's instructions for this line)
+ Send changes to repository: type ```git push origin master``` to send your committed changes.
+ To pull from GitHub: Use the command ```git pull``` to keep your version up-to-date with the remote version
