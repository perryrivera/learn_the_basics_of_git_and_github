# Learn the Basics of Git and GitHub

## Disclaimer
Every effort has been made to offer current and accurate information to our users, but errors can occur. We assume no liability or responsibility for any errors or omissions in the content contained in this presentation. This information is provided “as is,” with no guarantees of completeness, accuracy or timeliness, and without warranties of any kind, express or implied. We do not warrant that this presentation, various services provided through this presentation, and any information, software, or other material downloaded from this presentation, will be uninterrupted, error-free, omission-free, or free of viruses or other harmful components. To the fullest extent permissible pursuant to applicable law, we disclaim all warranties, express or implied, including but not limited to implied warranties of merchantability and fitness for a particular purpose.

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

## Re-generate a token
- Click your picture
- Click Settings. On the left hand menu, scroll down and click Developer settings
- Click Personal Access Tokens
- Click Tokens (classic)
- Click on the token you created about a month ago...
- Click Re-generate Token. 

## Installing git
- Check version of git
######
		git version
- See a version? Great!
	- If not, refer to: https://github.com/git-guides/install-git
 
## Configuring a staging area
- Define a spot to set up repositories. For this example, we'd like to make a directory under ~ called repo, i.e. ~/repo .
- Open up your favorite terminal app / shell
######
		cd ~

- Make a repo directory and cd into it...
- ######
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
######
		git config --list

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

## How to tag a file
- Use it to tag the last commit
- Simple Tag: git tag
######
		git tag release4
- Annotative Tag: git -a tag
######
		git -a tag v5.4.2 “Silver Edition Release v5.4.2”
######
		git log --one-line
######
		git tag -n

## Pushing the file to origin's repo
- Create a file
######
		git push --set-upstream origin master
- Enter username
- Enter password, which is a copy of your Personal Access Token. This is good for 30 days (or whatever duration you set previously..).

## How to create a branch

######
		git branch firstBranch
######
		git checkout firstBranch
######
		touch bugfix1
######
		touch bugfix2
######
		git add bugfix1
######
		git add bugfix2
######
		git stash
######
		git push --set-upstream origin firstBranch
######
		git checkout main

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

