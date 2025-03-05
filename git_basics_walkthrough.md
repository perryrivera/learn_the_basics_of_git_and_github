# Learn the Basics of Git and GitHub

## Set up Github.com
- https://github.com/
- Upper right-hand corner
	- **Sign up**
- Supply an e-mail, username, and password

## Generate a token
- https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token
- Click your picture
- Click Settings. Then, in the left-hand menu, scroll down and click Developer settings
- Click Personal Access Tokens
- Click Tokens (classic)
- Click Generate New Token
- Click Generate New Token (classic)
- For Note: Personal Access Token DD/MM/YYYY 
Expiration: (leave at 30 days)
Access: If it’s just you, choose toplevel checkboxes
- Click Generate token	
- IMPORTANT: Make sure to copy and secure your token in a vault, such as KeePassXC

## Installing git
- Check version of git
######
		git version
- See a version? Great!
	- If not, refer to: https://github.com/git-guides/install-git
 
## Configuring a staging area
- Define a spot to set up repositories. For this example, we'd like to make a directory under ~ called repo, i.e. ~/repo .
- Open up your favorite terminal app / shell
#######
		cd ~

- Make a repo directory and cd into it...
- #######
		mkdir repo && cd $_

	
## How to create a repository

- Click your **picture** then click **Your repositories**.
- In the upper-right hand corner, click the **New** button
	- Repository name: my-first-repo
	- Description: my-first-repo
	- Select **Private** (unless you plan to share, then select something else appropriate...)
	- Click **Create repository**

## How to associate local directories with your remote repository
- Create a directory to house the data from the remote repository
######
		mkdir myfirstrepo && cd $_
- Initialize the directory for the git application
######
		git init
######

		ls -al
######
		cd ..
  
## How to perform initial clone
######
		cd my-first-repo
- To figure out the URL link, go the place you'd like to clone, e.g. https://github.com/perryrivera/my-test-repo
- Click the green **Code** button
- Click the copy button to the right of the https url
- Note: For a private repo that your have access to, change github.com to username@github.com
- Paste the URL into the commands, such as git remote add origin https://github.com/janeuser/my-test-repo.git
######
		git remote add origin <URL>
######
		git clone <URL>
######
		git status
######
		git push

- See also https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository
- See also https://stackoverflow.com/questions/2505096/clone-a-private-repository-github


## How to add a remote repository to your local repository

- Switch to your repo directory
######
		cd ~/repo
- Use your **gitusername**

######
		git remote add origin https://github.com/mygitusername/my-first-repo.git
  
- NOTE: If you get error fatal: “not a git repository”, did you do a git init yet???

## How to set up global config
* While still in ~/repo/my-first-repo:
######
		git config --global user.email "my_email@gmail.com"
######
		git config --global user.name "First Last"

## How to stage and add files
- Create a file
######
		echo blah > this_is_my_first_textfile
- See what's in your directory
######
		ls
######
		git add <file>
######
		git commit <file>
- Enter commit message, e.g.
######
		Initial Commit

## Pushing the file to origin's repo
- Create a file
######
		git push --set-upstream origin master
- Enter username
- Enter password, which is a copy of your Personal Access Token. This is good for 30days (or whatever duration you set previously..).

## How to create a branch

######
		git branch firstBranch main
######
		git checkout firstBranch
######
		git stash
######
		git switch main

## How to cherry-pick files

- Find the commit you want
  
######
		git log <name of committed file>
- Copy the commit id into your clipboard
######
		git checkout featureBranch
######
		git pull
######
		git switch main

