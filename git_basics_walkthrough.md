# Learn the Basics of Git and GitHub

# Set up Github.com
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

# Installing git
- Check version of git
	- ```git version```
		- See a version? Great!
		- If not, refer to: https://github.com/git-guides/install-git
 
# Configuring a staging area
- Define a spot to set up repositories
	- ```mkdir repo && cd $_```
	
## How to create a repository

- In a browser, after changing username: https://github.com/username?tab=repositories
- In the upper-right hand side, click the New button
	- Repository name: my-first-repo
	- Description: my-first-repo
	- Select Private
	- Click Create repository

## How to associate local directories with your repository
- ```mkdir myfirstrepo coolproject```
	- ```cd myfirstrepo && git init```
	- ```cd ..```
	- ```cd secondproject && git init```

# Configuring git [part 2]
- ```cd myfirstrepo```
- ```git remote add origin <url>```
- ```git clone <url>```
- ```git status```
- ```git push```

# How to add a remote repository to your local repository

- Switch to your repo directory
	```cd ~/repo```
- Use your **gitusername**
	```git remote add origin https://github.com/mygitusername/my-first-repo.git```
- NOTE: If you get error fatal: “not a git repository”, did you do a git init yet???

## How to set up global config
* While still in ~/repo/my-first-repo:
	```git config --global user.email "my_email@gmail.com"```
	```git config --global user.name "First Last"```

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
