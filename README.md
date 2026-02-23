<img width="1675" height="140" alt="image" src="https://github.com/user-attachments/assets/1df606eb-5d05-4d07-a63c-75311b8b8494" /># GIT_Practice:
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
Now let's move on closer to git:

## SSH keys and Github
This section we will go over:
- Getting ssh authorization working
- Making a Github Repository 



### SSH

First thing to do to properly set up your Github is to acquire an SSH key. 
(Note this part is taken near verbatim from the Github website just witha few more pictures)
[https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
](GithubsInstructionPage)
First generate a key:

    ssh-keygen -t ed25519 -C "your_email@example.com"

This will prompt for a directory if you alread have a key just put in something like 

    /home/user/.ssh/SIAM

<img width="1667" height="296" alt="image" src="https://github.com/user-attachments/assets/8938fa01-4ece-4b94-a857-c8d4fcbb85a4" />

Then it will show something that looks like:

    SHA256:zhetsrhytuwdefwgiuqohkdfbhvsdkbyunmuyn user@email.com
    The key's randomart image is:

And then an ASCII art square.

We have now generated an ssh key pair so that Github can verify the identity of your computer.

But now we have to give the "lock"(public key) to Github so that it knows to ask to verify your identity.

First we have to get the public key:

        cat ~/.ssh/SIAM.pub
This will print the key to eth terminal so that you can copy it (using CTRL-SHIFT C because terminals are annoying like that). 

Then we had to add this to our GitHub account,

0. Sign in to Github.
1. Click on your your profile in the top right corner (mine is the red and white thing):

<img width="973" height="440" alt="image" src="https://github.com/user-attachments/assets/374a8289-2d21-446f-9d0a-77374104de65" />

2. Click on the settings button:
   <img width="396" height="820" alt="image" src="https://github.com/user-attachments/assets/b071708d-a8b8-4542-aaea-e4622360fac4" />
3. Click on SSH and GPG keys:
   <img width="411" height="845" alt="image" src="https://github.com/user-attachments/assets/4ad5cdf6-6639-4644-aefb-9c89cd4e6fe6" />
4. Click New SSH Keys<img width="1258" height="81" alt="image" src="https://github.com/user-attachments/assets/246cd9b8-f8fd-450b-923b-1927676d4879" />

5. Then Name the SSH key something like SIAM_PRACTICE_KEY and paste the key you copied from the terminal into the little box:
 
<img width="1207" height="635" alt="image" src="https://github.com/user-attachments/assets/82b06ca4-5146-4ea1-8787-07127863a4b4" />

6. Press the big green button that says Add SSH key and then authenticate your identity again (I suggest hitting the type in password button)

And there you have it SSH keys!!!

### Making A Repository

Now we are going to actually make a repository: 
Open a new Github tab or hit the home button.
Then hit the big green button on the top left that says New:

<img width="403" height="273" alt="image" src="https://github.com/user-attachments/assets/0efa0864-1463-4946-b614-aa2bcc70fbb1" />


Next I suggest using a README and a GPL liscense but minimally give your new repository the name 

    GIT_Practice

<img width="1066" height="922" alt="image" src="https://github.com/user-attachments/assets/9bc866d8-09b7-4635-82c0-875b0778e07d" /> 

Now hit the big green button that says Code make sure it is on the SSH tab and click the copy to clipboard button:

<img width="1825" height="1001" alt="image" src="https://github.com/user-attachments/assets/996a0e7c-99e3-4cff-b82f-01f6c4da6823" />

Go back to your terminal type:

    git clone

And then paste with CTRL-SHIFT-V to get something like 

    git clone git@github.com:NoahUnger-Schulz/GIT_Practice.git

it should show you something like this:

<img width="1853" height="385" alt="image" src="https://github.com/user-attachments/assets/cdfadd4b-885c-4f7d-863a-1a408c276c18" />

If you ls you should see the GIT_Practice directory so then type cd and tab or just paste:

    cd GIT_Practice

It's always good practice to ls and just make sure that the Liscense and README.md are there:

<img width="1813" height="152" alt="image" src="https://github.com/user-attachments/assets/28fbe7ee-1b88-4cd6-ab0d-da015fa50021" />

If so you have cloned the repository.

## General Git

The first thing you should do when working with git is pull work from the remote repository.

    git pull

In other words you want to ensure that the code on your computer (or local repository) 
is the same as the code on Github (the remote repository).
As you just used the git clone command this should just say "Already up to date."

Now let's write some "code"!!

First we create a branch.

    git checkout -b Branch1

The idea of git is that it is a tree graph of different people's code 
when you make a new thing you put it on a branch so that then two people aren't editing the same file.

To see your branches type:

    git branch


You should see the main branch and your new branch Branch1

<img width="882" height="151" alt="image" src="https://github.com/user-attachments/assets/ab8c1711-dfd5-4c0e-9742-bfc4ebeb4369" />


Then we open a file called code.txt

    vim code.txt

Write something like:

    This is my first git branch

To add this file to the branch we are in we use the git add command

    git add code.txt

If you are lazy you can also do:

    git add .
To add all files in your current directory(the folder you are in) to the branch at the same time

To make sure you did this right type:

    git status

<img width="971" height="266" alt="image" src="https://github.com/user-attachments/assets/82b8eac0-0766-4b1d-b9d9-04221fcd4a7a" />

Your code is currently "staged" this means that it is being tracked by git but has not been commited.
Let's add a second line that says 

    Un-staged code
to our code.txt file.

Now your status should look like this:
<img width="1353" height="468" alt="image" src="https://github.com/user-attachments/assets/2bc8c5b1-6bef-45f6-b202-183727cf345b" />

Where there is staged and unstaged code.
Now lets commit the code so that our local git will remember our changes.

    git commit -m "Committing our staged changes"
(The "-m" stands for message so that our commit gives inforamtion for us to come back to )

Then if we git status again we get:
<img width="1342" height="345" alt="image" src="https://github.com/user-attachments/assets/42c48be6-9ec5-4004-ab1f-a900836e0cd1" />

To see what of our code is unstaged I like using:

    git diff



This will return the green unstaged line and a white unchanged line.

<img width="1342" height="345" alt="image" src="https://github.com/user-attachments/assets/8af2787e-1bca-4618-b762-fe93ebf0610d" />

Now delete the word first in the top line and use git diff again 
<img width="1326" height="382" alt="image" src="https://github.com/user-attachments/assets/ae1166f7-bea1-4696-ba0c-6ab0f7dabb4e" />

The top line now has a red deleted version and a green new version. 

We can add and commit at the same time with the a flag:

    git commit -am "adding unstaged changes and committing them simultaneously"

Now our git diff should be blank and our git status should say something like 

    On branch Branch1
    nothing to commit, working tree clean

Now Let's look at git log to see what our previous commits look like:

    git log

<img width="1537" height="765" alt="image" src="https://github.com/user-attachments/assets/e4590f1c-eb45-4a1a-81f3-0f1836a5f915" />

Now that we have minimally a few commits we can start using the cool parts of git: Time travel!!!
Suppose we want to look back at our old code. We can simply checkout the previous commit with:

    git checkout HEAD^
Looking back at git log it should be one commit shorter

<img width="1522" height="550" alt="image" src="https://github.com/user-attachments/assets/0a008bcb-66e6-4ca4-80d8-492d5fc6999c" />

If we look at our code it should be what it said before we commited it:

    This is my first git branch

Magic!!!
There is a downside to this: we are currently in a detached head state take a look at
    
    git branch
<img width="981" height="218" alt="image" src="https://github.com/user-attachments/assets/ffc1231e-db7b-458b-a787-6dcc4c36d79c" />
We are neither in main or Branch1! To fix this let's:
    
    git checkout -b Branch2

Now to understand what our timeline looks like a little bit better we can use 
    
    git log --all

To see all the branches at once.

You can make it even fancier with 

    git log --all --decorate --graph

<img width="1626" height="853" alt="image" src="https://github.com/user-attachments/assets/ce6fbe7c-cde3-4aeb-b2cb-34a3fc0a69a8" />

Although often people make this have less verbose output and set it to an alias like so:

    git config --global alias.adog "log --all --decorate --oneline --graph"
    git adog
I kinda like the verbose mode so I also made:

    git config --global alias.adg "log --all --decorate --graph"
    git adg

Anyways this shall be more useful in a bit once our git gets more complicated.
