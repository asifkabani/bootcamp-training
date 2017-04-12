## GitHub

Create a repository by visiting github.com and clicking on creating a new repository.

**If you have a local folder created for this repository already use the second version it gives you:**

```
git remote add origin https://github.com/username/first_push.git
```

A ```remote``` is a copy of your local repository which is held somewhere else. You can push changes to a remote or pull changes from a remote to make sure that your local and remote repositories stay in sync. You can have more than one remote for a single repository. For example, you may have a remote which belongs to a collaborator so you can pull changes they have made into your local repository. Or you may have a separate remote which you will push to in order to deploy the latest version of your code.

Here you are creating a remote called ```origin```. This is the name that is conventionally given to your main remote. You should push changes up to your origin remote on a regular basis so you have an up-to-date backup of your code and its history.

**Push your commits to the GitHub repo**:
```
git push origin master
```
This command is doing a couple of things. First, it will create the master branch in the remote repository because it does not currently exist. Then it sends the most recent snapshot of the newly created master branch so the copy on GitHub matches our local copy.
