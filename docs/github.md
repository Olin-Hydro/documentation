# Github

_This part is basically just the onboarding!_

## Installing Github
_You might be thinking "I'm not a programmer, I don't need this," get it :3_

1. Download **Git** for your os [here](https://git-scm.com/downloads).
2. Run the file with default settings. Make sure that git is added to your computer's PATH.
3. Download *Github Desktop* [here](https://docs.github.
com/en/enterprise-cloud@latest/desktop/installing-and-authenticating-to-github-desktop/installing-github-desktop).

    _This step is **not** optional for advanced users. Unity is not command line friendly when it comes merging branches._

4. Run the installation file and log in.

    _If you haven't already now is a good time to create a github account._

5. Select "Clone a Repository from the Internet".  Paste "https://github.com/lilibaker/outmaine.git" into the space for a web adress. Make note of file path that the repository has been copied to. You will need it in the next step.

    _If this throws an error, reach out to Kenneth. You don't have access to the repository(oops!)._  

6. Open Unity Hub. Click "Add Project" and select "From Disk". Nagivate to where you cloned repository earlier. If everything was setup correctly, the project should open in Unity. YAY!!!!

## Commiting and Pushing Changes

1. Go  to GitHub Desktop.

2. At the bottom left, there's a text box that says "summary(required)." This is a commit message. This goes alongside your files that are uploaded to Github. This is how developers keep track of what changes have been made. It's important to leave a quick helpful message such as "Finished onboarding scene" or "added background". Write a quick message and click commit.

3. Click the box next to "Current Branch." For new branches it will say "Publish this branch," while for old ones it will say "Push origin".


## Creating a New Branch

1. Select the "Current Branch" drop down again.
2. Click "New Branch" to the right of the search bar.
3. Name the branch. 
4. Under "Create branch based on..." make sure your new branch is highlighted and not "main."

If all goes well, it should say the name of your branch under "Current Branch."

## Switching Branches

1. Open the repository in Github Desktop. If you just did the setup, you should already be there.
2. At the top of the window there should be three boxes of text all in a line: "Current Repository," "Current Branch," and "Fetch Origin". Click on "Current Branch."
3. Select the your branch. If it doesn't show up, search for it in the search bar. 

_If upon switch branches, you receive a popup for resolving changes select "Leave changes on main."_

_If you get an "Overwrite Stash" prompt select "overwrite"_

## Merging Branches

Merging branches to be pulled into main is a massive headache. For now, the steps are try to merge the branch. If it fails, talk to Kenny, we'll work on it together.

1. To merge your branch onto a another one, commit and push your changes and switch to the branch you want to merge into.

2. Go to Branch > Merge Into Current Branch and select the branch you were working on.

3. Create a merge commit.

That should just work, if it doesn't.... STOP!

We'll look at it together!