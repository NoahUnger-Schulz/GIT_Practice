# GIT_Practice:
Welcome to the OSU SIAM chapter Git Workshop.
This workshop will hopefully go over:
- Basic Unix Terminal Usage
- SSH keys and Github
- General Git
- Other things that will be more apparent later

## Opening A Terminal

A lot of git is used in the terminal and it leads to in my opinion a very fast work flow.
First thing we will want to do is open the terminal. 
The terminal is just an app and be started like any other. 
For windows there is powershell, for mac and linux there is a terminal app.
Mine looks like this:
<img width="1537" height="973" alt="image" src="https://github.com/user-attachments/assets/1bab2913-94f6-4770-9a99-1ec0686df23d" />

Now for this project let's create a new directory using the make directory command 
    
    mkdir SiamGitPractice

and then change into it using the change directory command:

    cd SiamGitPractice

Next you should try to open up your text editor from the terminal.

I like using vim:

    vim hello.txt
To type in vim press i to enter insert mode, the Escape :wq when you want to save your work.
(Also note that in vim you have to use CTRL-Shift-C/V for copy and paste)
There are lots of other fancy things in vim that allow you to type faster but we shall not get into them.

You can also use vscode or nano if either of these are setup on your device:

    nano hello.txt
    code hello.txt


Now to check that it saved list all the things in your directory with ls:

    ls

Now let's remove the file:

    rm hello.txt

and ls again to find an empty directory.


Yippee! We now know all the bare-bones Unix commands.


## SSH keys and Github
This section we will go over:
- Getting ssh authorization working
- Making a Github Repository 



### SSH

First thing to do to properly set up your Github is to acquire an SSH key.

First generate a key:

    ssh-keygen -t ed25519 -C "your_email@example.com"

Then 


<img width="1066" height="922" alt="image" src="https://github.com/user-attachments/assets/9bc866d8-09b7-4635-82c0-875b0778e07d" /># 
## General Git

