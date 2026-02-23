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

