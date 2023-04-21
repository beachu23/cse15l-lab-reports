Hi! Welcome to my tutorial on how to remotely access git through VSCode. The first step is to download VSCode at this link:

[Link](https://code.visualstudio.com/download)

When you've finished downloading, you should see something like this:
![Image](Screenshot%202023-04-06%20113936.png)

(My VSCode is brown because I changed the color)

Then we want to download an application called GitBash. The link to download is as provided:

[Link](https://gitforwindows.org/)

Git is used for version control, and is useful if multiple users need to access the same system.
After git is downloaded, open a new terminal in VSCode. Select the dropdown menu next to the + sign on the upper right hand side of the terminal. 
Click "Select Default Profile". There, you should see GitBash appear as an option. Select GitBash as your default terminal. Then, open a new terminal and 
type the following:

    $ ssh cs15lsp23**@ieng6.ucsd.edu, 

where the asteriks are replaced by the rest of your personal username. The terminal will then prompt you for your password. 
Additionally, if you just set your password, it might take 10 minutes or so for the change to take place, like it did for me.
Type in your password, but note that the letters you type will not appear on the terminal. You should then see this:
![Image](Screenshot%202023-04-06%20114027.png)

(Note, if this is your first time on the current OS, you may get a warning message)

Afterwards, you can play around with some commands:
![Image](Screenshot%202023-04-06%20114000.png)
cd, ls, cat, and cp are some examples.

I tried to cd into the only directory provided but it didn't work? So I'm not completely sure on how it works. 

Congratulations! That's all for the tutorial.


