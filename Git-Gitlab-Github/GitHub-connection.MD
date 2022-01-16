For Connecting your personal laptop or PC to your github account

1- install git 
2- configure your accounts with
$ git config --global user.name "Your name here"
$ git config --global user.email "your_email@example.com"
$ git config --global color.ui true
$ git config --global core.editor "code --wait"

3- Look to see if you have files ~/.ssh/id_rsa and ~/.ssh/id_rsa.pub.
If not, create such public/private keys: Open a terminal/shell and type:

$ ssh-keygen -t rsa -C "your_email@example.com"
Copy your public key (the contents of the newly-created id_rsa.pub file) into your clipboard. On a Mac, in the terminal/shell, type:

$ pbcopy < ~/.ssh/id_rsa.pub
Paste your ssh public key into your github account settings.

4-Go to your github Account Settings
Click “SSH Keys” on the left.
Click “Add SSH Key” on the right.
Add a label (like “My laptop”) and paste the public key into the big text box.
In a terminal/shell, type the following to test it:

$ ssh -T git@github.com
If it says something like the following, it worked:

Hi username! You've successfully authenticated, but Github does
not provide shell access.

5-Click on the Spotlight icon (magnifying glass) on the right side of the menu bar. Type Keychain access then press the Enter key to launch the app => In Keychain Access, search for github.com => Find the internet password entry for github.com => Edit or delete the entry accordingly => You are done

