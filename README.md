# GitHubHelp

You will need to create a new repository on GitHub website.
Use cd to navigate to the local project directory that you want to publish on GitHub.

git init

git add .

git commit -m "First commit Message"

git remote add origin GitHub-repository-URL

At first glance it looks like you have got your master and Heroku parameters round the wrong way because the first parameter to git push should be the name of the remote repository, the second is refspec (normally a branch). You are more likely to have a branch called master and a remote called Heroku. But I would expect you to get a different error message if that were the case, something like:

fatal: 'master' does not appear to be a git repository
fatal: Could not read from remote repository.

The error message you are seeing implies that there is no local master branch. That would be the case if you haven't made any commits yet because git doesn't create the branch until the first commit. You can check this by running:

git show-ref

You should see a line containing refs/heads/master if you have a master branch. If not then try running:

git commit -m 'Initial commit'

You can also find out what remotes you have available with:

git remote -v

If you have a remote called Heroku you should see something like:

Heroku  git@heroku.youraccount:yourproject.git (fetch)
Heroku  git@heroku.youraccount:yourproject.git (push)
