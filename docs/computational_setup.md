# Computational Setup

For this computational setup, we’ll be using Ubuntu as our operating system. This requires dual booting on Windows 11 with Ubuntu 22.04 LTS

<aside>
📝 *This guide is mainly written for Ubuntu users so you may encounter issues otherwise*

</aside>

[Setup for Windows](https://www.notion.so/Setup-for-Windows-21768805f3174ebe9528ec47d72f819c?pvs=21)

### Installing Ubuntu

1. Make partition for installing the OS

- Go to your disk management tool on windows.
- Select your biggest partition (by default the C drive)
- Click “Shrink Volume”
- Shrink 50gb → go to IT if the shrink fails
- Create a new partition

1. Acquire a bootable USB that has the Ubuntu image
2. Restart the computer and enter BIOS settings (Press F2)

- Select the USB with Ubuntu image as the primary boot loader
- Disable Secure Boot if enabled
- Save and exit

1. When the computer starts again, select “Try/Install Ubuntu”

- Stick to the default settings EXCEPT the partition to install Ubuntu on
- Make sure that the selected partition matches the size of the partition you created earlier
- Continue until the installation finishes

## Install VSCode

- Download and install VSCode for respective OS

[](https://code.visualstudio.com/download)

## GitHub Setup

- First make an account if you haven’t already!
- Tell me (@dedeisnerd on discord) your GitHub username
  - I’ll add you to the Olin-Hydro organization on GitHub

## GitHub SSH Setup

<aside>
📝 SSH lets you authenticate yourself without having to login to GitHub every single time with username and password. SSH key will be a unique key for your machine, which will be added to your GitHub account — GitHub will then recognize your machine to your user account.

</aside>

1. Create an SSH key on your local machine

   `ssh-keygen -t ed25519 -C "your_email@example.com"`

2. Add that key to your local ssh key agent

   `eval "$(ssh-agent -s)"`
   `ssh-add ~/.ssh/id_ed25519`

3. Add that key to your GitHub account

   `cat ~/.ssh/id_ed25519.pub`

   → Running the line above will return a long string of alphabets and numbers, followed by a space and the email that you entered. Copy the content of this key file by dragging the string and pressing `Ctrl+Shift+C` (`Ctrl+C` will not work on Ubuntu terminal).

   - Now, go to your GitHub account settings. Click on the “SSH and GPG keys.”
   - Click “New SSH key or Add SSH key”
   - Paste the copied key
   - Give it a descriptive name, like “Olin Laptop Ubuntu”
   - Click “Add SSH key”

- Confirm the authentication
  `ssh -T git@github.com`
  → Running this command should say something like “you have authenticated.”

_More information from GitHub:_ https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

## Git Setup

### Configuring Git for you

- Run the command `git config --global user.name "Alan Turing"`, substituting your name for `Alan Turing` (but leaving the quotes in place).
- To set your email, run `git config --global user.email "alan@turing.org"`, substituting your GitHub email address for `alan@turing.org`. It’s important that your email match the one that GitHub has, because a mismatch can make Git fail in unintuitive ways.
- To set Git to use VS Code, run `git config --global core.editor "code --wait"`. Again, leave the quotes in place.
- If you mistyped anything in quotes (your name, email, or `code --wait`) you can run that command again with the correct name/email to fix the typo. If you mistyped `user.name`, `user.email`, or `core.editor` in the commands, you can use `git config --unset user.name` (replacing `user.name` with whatever you mistyped earlier) to remove that setting, and try again.

_The information above was taken from Configuring Git section of Olin’s SoftDes website:_

[Computational Setup Instructions](https://softdes.olin.edu/docs/setup/setup-instructions/#configure-git)

## Install Anaconda

\*Anaconda is a package manager and it will save you from having dependency errors when working with complex packages. Rule of thumb is to always try to use the same package installer. [Installation link](https://docs.anaconda.com/free/anaconda/install/linux/)

If you’re using Ubuntu or MacOS, once you’ve downloaded the program, run:

```bash
# Change the directory to where the download is!
$ bash ~/Downloads/<Anaconda3-some-version-xx>.sh
```
