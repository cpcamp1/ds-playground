## Prerequisite - Introduction to Git and Github

### Simple Overview
In this section we are going to start getting familiar with Git and Github. Git is a tool that allows developers to version control the projects that they are working on. At a super high level it works like this:
1. You have a project that contains files, images, code, etc. The source of truth of this project is called the `main branch`.
2. If a developer wants to make a change to the project they will create their own unique copy of the main branch and choose a name of their choice for it. Example: `adding-feature-x`.
3. The developer makes their changes on this copied branch.
4. The developer submits a `pull reques` in order to make their branch the new `main` branch. In simple terms, a pull request is simply asking other developers on the project to review the changes that you've made and either approve or decline making your branch the new main branch. If approved, then the developer can `merge` in their branch which will make it the new main branch. His/her code changes are now part of the source of truth.

The main advantages of this type of workflow is that you can make code changes to your branch without having to worry at all about causing issues with the source of truth. If at any time you need to abandon the changes that you're working on you can just delete your branch, start over or move on. For small, solo, projects developers do sometimes make their changes directly on the main branch. However, when working with a team this is highly discouraged. At RV many teams disable the ability to make changes directly to main.

After this, you can continue making more changes or go online to Github and create your pull request.

### Videos
Please watch the following Git lessons to get a deeper understanding: (Note: when setting up your Github account, most people at RV prefix their username with "rv-" in order to keep their rv account separate from their personal account.)

* [Github Ultimate Course](https://redventures.udemy.com/github-ultimate/learn/lecture/4731904#overview)
  * Sections 1-4, 6-7

### Additional Github setup required for RV
1. First, please go to https://github.com/ and create an account if you do not have one already. Use your redventures email and select the free account. It is common to prepend your username with `rv-` and keep your RV Github account separate from any personal Github accounts that you may end up creating.
2. Follow the following process to enable two-factor authentication: https://help.github.com/en/articles/configuring-two-factor-authentication
3. Please submit a request ticket for RV GitHub Organization authentication by going here: https://redventures.service-now.com/sp?id=sc_cat_item&sys_id=0e473571dbfbc494e987e3a84b9619ec
4. This request is sent to your manager for approval. It can take up to an hour for AD/OKTA to sync. When this is approved and completed, you can view the github tile in your OKTA applications (https://redventures.okta.com/app/UserHome)
5. You can use this tile to access github for the first time to sync your AD/Okta account and your github account.
6. You will receive an email from GitHub titled `[GitHub] @rv-bot has invited you to join the @RedVentures organization`. Go to your email inbox and click on Join @RedVentures.

#### SSH Keys
SSH Keys are access credentials that allow your local machine access to access Red Ventures remote repositories on Github.

##### For MAC Users:
To create an SSH Key, go to your terminal (or iTerm 2) and enter `ssh-keygen`. You will be prompted for a file in which to save the key (.ssh/id_rsa). There's no need to enter anything, just press enter. When prompted for a passphrase, you can enter one or just press enter to ignore creating a passphrase.

Your SSH key has been saved to ssh/id_rsa.pub, run the command `pbcopy < ~/.ssh/id_rsa.pub` to copy this to your clipboard. 

Now go to your Github account setting for Key: https://github.com/settings/keys and click `New SSH key`. Add any title you want, like `First SSH Key`, paste in your SSH key, and click the `Add SSH key` button. 

Lastly, authenticate your SSH Keys for SSO use by clicking the `Enable SSO` button for any keys that will be used within our Organization. Click the `Authorize` button next to the RedVentures organization

##### For PC Users:
To create an SSH Key, go to your terminal and enter `ssh-keygen`. You will be prompted for a file in which to save the key (.ssh/id_rsa). There's no need to enter anything, just press enter. When prompted for a passphrase, you can enter one or just press enter to ignore creating a passphrase.

Your SSH key has been saved to ssh/id_rsa.pub, run the command `cat ~/.ssh/id_rsa.pub` to see your SSH key in the proper format. Copy the whole text string starting with 'ssh' to the end.

Now go to your Github account setting for keys: https://github.com/settings/keys and click `New SSH key`. Add any title you want, like `First SSH Key`. Paste your SSH key to the Key window, and click the `Add SSH key` button. 

Lastly, authenticate your SSH Keys for SSO use by clicking the `Enable SSO` button for any keys that will be used within our Organization. Click the `Authorize` button next to the RedVentures organization

### Homework:
For the homework assignment, we are going to setup your personal Homegrown Data Science repository and get familiar with the above commands.

#### Setting up a new project
1. Go to github.com and click `New` to create a new Github repository.
2. Select RedVentures as the owner and name your repository in the form `rv-username-homegrown`. 
3. Select the `Private` option ("You choose who can see and commit to this repository.")
4. Initialize the repo with a README and click "Create Repository"  
5. Go to `Settings` -> `Collaborators and teams` -> `Add teams`, grant read access to team `homegrown-2023-faculty` to your homegrown repo.  
6. Click on the green "Code" button and copy the url to your newly created repo. (Make sure it's the SSH url --you can toggle it at the top right of the popup modal)
7. Open up your terminal and navigate to a directory that you want your project to live in.
    * `ls` will show the files and folders in the current directory
    * `cd name-of-folder` will "change directory" into whatever folder your name
    * `cd ..` will move up a directory.
    * Google "how to x in bash" if you need to figure out how to do anything unique in the terminal, like make a directory (folder)
8. Run `git clone url-that-you-just-copied`
9. Run `ls` and you should now see the name of your newly created repo. `cd` into this repo.
10. You can now open your project with Textmate, VS Code, Sublime or any other editor of choice. VS Code is my personal favorite.

#### Making changes to the project
There are a lot of complex functionalities of Git, but for 99% of work there are 4 things that you need to be able to do:
1. Create a branch `git checkout -b my-branch-name` 
2. Add files that you want to queue up for saving. 
    * To add all files: `git add .`
    * To add a specific file: `git add path-to-file`
3. Save (commit) changes to the files that you added above. `git commit -m "message about this commit. Ex: change button color to green."`
4. Sync your branch to Github so that you can later make a pull request. `git push -u origin my-branch-name`

As a challenge, use the commands above to:
1. Create a new branch called `first-project-addition`
2. Now, go to your editor, open up the README.md (create a new file with this name if it doesn't already exist) and create a subheading-2 in markdown that says "Week 1:" In the line below that copy and paste your RV profile link, e.g. https://arvy.io/employee/2358.
3. Go back to terminal and run `git status` to see any files that you've modified.
4. Add the readme file that we just updated (# 2 in the section above).
    * if you run `git status` again after you should now see that your README.md file is "to be committed." Which simply means that it's ready to be saved.
5. Commit the changes with the commit message "initial commit."
6. Sync ("push" is the real terminology) your branch and changes up to Github.
7. Go back to your repository on github.com and figure out how to create a pull request. (If you go to the site shortly after completing the last step Github should automatically prompt you to create a pull request.)
    * Side note: once you create a pull request you can click on the "Files changed" tab to see all of the items that you've just added.
8. Merge your branch with main.
9. Congratulations, the changes that you made are now part of the main branch!
10. Finally, go back to your terminal and switch back to your main branch with the command `git checkout main`
    * If you look at your project in your editor after doing this you'll notice that your changes are gone!
    * The reason for this is because when you first cloned the main branch those changes were not a part of it. If we run the command `git pull` then terminal will go up to Github and bring in the most recent version of the main branch. So, run that command and your recent changes should now appear in your editor.
11. Next time you need to add items to this repository you can go through this same process. If you want, for future additions you can skip the part where you create a new branch and just do everything directly on the main branch. However, it's probably good practice to do this a few more times. Also, if you do make changes directly to main, once you sync (push) your changes up to Github then you are done. No need to perform a pull request.

### Supplemental Materials:
Here is a handy git cheatsheet: https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf.
