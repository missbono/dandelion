# GITHUB TUTORIAL

## GitHub
[Create a new Github account](https://github.com/) if you do not already have one. You can use your GA email or your personal email if you are comfortable doing so.
1. Get your personal access token (a special kind of password) from GitHub and save it somewhere
2. On GitHub.com,
Settings → Developer Settings → Personal access tokens → Tokens (classic) → Generate
3. Check repo, delete_repo, and admin:repo_hook
4. Expiration: set to 06/01/2026
5. Make sure you save the resulting personal access token (which is just a randomly generated string) somewhere safe and accessible!

## git
[What is git?](https://launchschool.com/books/git/read/introduction#whatisversioncontrol)
Installation
1. Check if git is already installed. In a Terminal window, type:
```
git --version
```
1. If you do not see output telling you which version of git you have, [install git](https://git-scm.com/downloads/mac) on your Mac (select the binary installer OR use [Homebrew](brew.sh)).
    1. If you see an error message, go to System Preferences → Security & Privacy → General, under "Allow apps downloaded from:" select the final option that allows you to run the git installer.
2. Make sure your Terminal understands the "git" command:
```
echo "PATH=/usr/local/git/bin:\$PATH" >> ~/.zshrc
```
3. Make git remember who you are! (Use the email you signed up for GitHub with.)
   
```
git config --global user.name "Your Name"
```
```
git config --global user.email "your_email@whatever.com"
```
4. git by default creates new "branches" with the name "master", but GitHub.com uses "main". Fix this with:
```
git config --global init.defaultBranch main
```
### Make a new local directory
1. Create a new local directory in a location of your choosing, e.g. on your desktop
2. Name it "hello_world"
3. Create a ```hello.txt``` file in your local hello_world directory
4. Use ```nano hello.txt``` to add some text in your file!
   1. (Control+X, Y, RETURN to save! How can we make sure the changes worked?)
### Connect your (local) repository to GitHub (remote)
1. **While in your hello_world directory** (hint: use pwd to confirm)...
```
git init
```
1. Tells the computer you want to repo to be a git repository, not just a local one. (Use ```ls -a``` to check that it worked!)
   1. you should see a few new directories! (.git, .., etc)
1. Inform the computer you want to "track changes" for the hello.txt file.
```
git add hello.txt
```
3. To make sure we "staged" our changes:
```
git status
```
4. Label this "commit" with a message summarizing the changes you have made. (e.g. "adds hello starter file")
```
git commit -m "[YOUR MESSAGE GOES HERE]"
```
5. If you are getting weird feedback that says ```dquote>``` hit ```control + X``` and redo the commit command with single quotes

### Link this git repo with a remote repo on GitHub.com
1. Go on GitHub.com and create a new repository there.
2. Name it hello_world for convenience, though it does not need to match your local repository's name
3. Under "Initialize this repository with…", do not check any of the options for creating files
4. Once created, click green "Code" button on main repository page and copy the resulting URL: should look something like "https://github.com/[YOUR USERNAME]/hello_world.git"
5. Back in the Terminal in your local hello_world repository, run:
```
git remote add origin [URL FROM STEP B ABOVE]
```
6. Rename the main branch of your git repo to "main":
```
git branch -M main
```
7. "Push" your changes to the cloud/remote repo:
```
git push -u origin main
```
8. You will be asked to enter your GitHub.com username and the personal access token you created earlier. (*note: NOT your password)
9. Now check your GitHub.com repository - you should see the file that you pushed! Yay!

Which steps do you need to repeat every time you create a new local directory/project?
Which steps do you need to repeat each time you add, modify, or delete a file within an existing git repo?

#### Getting new changes from the remote repo
Check if there have been changes to the remote repo (on GitHub) that are not reflected in your local repo.
```
git fetch
git diff main origin/main
```
Get the changes from the remote repo (origin/main):
```
git pull
```

#### When you want to work on a remote repo that you do NOT yet have a local copy of
1. Navigate to the GitHub repository site, e.g.: https://github.com/missbono/dandelion 
2. Click on the green "Code" button and copy the URL, e.g.: https://github.com/missbono/dandelion.git
3. In Terminal, go to the (local) directory that you want your new repository to live within (e.g.: your "CS_Honors_Seminar" folder).
```
git clone [URL FROM STEP 2] 
```
4. This creates a local git repository in your current location, downloads everything from the remote repo onto your computer, and connects the local repo to the remote one.


