Guide to Git:

Git is a Version Control System for tracking changes in computer files.

It also just stores files.

Git is a distributed version control system. It allows many developers work on the same project simultaneously without being on the same network. It coordinates work between developers and tracks every change that is made on the system. 

Usually with Git, you have a repository on your local machine/laptop/PC that you use to manage changes and you push it to a remote repository such as GitHub. You do not need an internet connection to work on a project locally and you can make changes but if you want to push it to the remote repository you need an internet connection.

Reasons to use Git:
- Keeps track of your code history
- Takes 'snapshots' of your files
- You decide when to take a snapshot by making a 'commit'
- You can visit any snapshot anytime
- You can stage files before committing - this is done with an 'add' command

Once you make a commit, other developers can pull your code onto their machine.

Basic Commands:

$ git init - will initialise a Git repository on your machine. It will create a .git folder in the project your terminal is in. It's hidden by default.

$ git add <file> - will add the file(s) you specify to the 'staging' area/index and will be ready for commit. This can be run as many times as needed before committing to the repo and Git will just store the files in this staging area.

$ git status - Will display the status of the Working Tree.

$ git commit - take everything in the index/staging area and put it into the Index area.

$ git push - will push a project to a remote repository (such as GitHub)

$ git pull - pull the latest changes from a remote repository

$ git clone - will pull/download a remote repository into a new folder/directory

$ git --version - will tell you the git version installed on Mac

Installing Git:
For Mac: http://git-scm.com/download/mac



When creating a project, you must run 'git init' in order to run git commands.

You can also add you name and email to Git's configuration:
$ git config --global user.name 'Alan Campbell'
$ git config --global user.email 'alanjamescampbell1@gmail.com'

To add a file to the staging area go:
$ git add index.html

To view all files in the staging area go:
$ git status

To remove a file from the staging area go:
$ git rm --cached index.html

To add all HTML files in a folder:
$ git add *.html

To add every file:
$ git add .

If we edit a HTML file, save and run git status, we will information in relation to the 'Changes not staged for commit'.

When we commit a project to Git, the terminal will open a new editor, vi.
Press 'I' to go into insert mode and this will allow us to add comments beside the # symbol.

To get out of insert mode press 'esc'.
To get out of the vi window type ':wq' and press return.

If we type 'git status', it will now say nothing to commit.

To skip the editing stage with the vi terminal when using the Git commit command we type:
$ git commit -m 'Changed app.js'

Git Ignore:
This command creates a file that stops certain files from being added and committed to Git. Even if you use the 'add .' command.

Create the .gitignore:
$ touch gitignore

If you cannot see .gitignore in the finder on Mac, open a new terminal and type:
defaults write com.apple.finder AppleShowAllFiles TRUE

Then relaunch the finder with:
killall Finder

Open the .gitignore and type in directly the name of the files you do not want included, e.g. log.txt

So if we go 'git add .' and 'git status', the file names included in .gitignore are not there.

.gitignore can also be used on entire directories. This can be achieved by including the line '/dir1' in the .gitignore folder.

'*.txt' in gitignore will stop all text files from being added.


Branches:
Say you are working with a group of developers and you are tasked with the role of creating the log in. 
You can create a branch called 'logIn' that you commit to and this will not effect the main branch which will be the final project, aka the Master Branch.

Create a Branch:
$ git branch login

Open up into the branch:
$ git checkout login

Creating a file in login branch:
$ touch 'login.html'

To go back to the Master branch go:
$ git checkout master

When we switch between Master and login branches the finder folder changes too.

To merge a login branch with the master branch go from the master branch:
$ git merge login
Note: issues will arise with files that have the same name, different content are trying to be merged together.


Add to GitHub:
To add a remote repository from GitHub, in the master branch run:
git remote add origin https://github.com/alancampbell1/myGitApp.git

Then in the terminal go 'git remote' and it will return 'origin'. 

Then to push to the remote repo go:
git push -u origin master

So now every time you edit a file and go 'git push' the file will be added to the GitHub repository.

Clone a Repository:
Make your own local version of a GitHub repository on your own PC:
$ git clone https://github.com/alancampbell1/myGitApp.git

To make sure you have the latest version you can go:
$git pull
Git will tell you if everything is up to date







