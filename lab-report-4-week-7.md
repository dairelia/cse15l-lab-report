# First Task
## Task Chose: 
In DocSearchServer.java, change the name of the start parameter of getFiles, and all of its uses, to instead be called base.
## Shortest vim Command:
:%s/start/base < enter > < ESC > :w

total of 17 keypresses
- First cursor move:
the ":" keypress removed the cursor and waits to change the mode
![image](vimcoloncmd.png)
- Second cursor move:
the "%s/start" keypresses searched for all "start" in this file and moved the cursor to highlight the first "start" in the file
![image](vim2.png)
- Third cursor move/changed the text:
the "/base < enter >" keypresses deleted all the "start" in the file and replaced them with "base"
![image](vim3.png)
- Last cursor move:
the "< ESC > :w" goes back to normal mode and saves the changes
![image](vim4.png)

# Second Task
1. Visual Studio Code: 273 seconds 
2. SSH and then vim: 366 seconds, this method took longer because I'm not as familar to the vim commands yet, and I tend to mix up the h j k l keys.

## Which of the two methods would I prefer use?
I prefer using the second method if I were to do this remotely, ssh and the vim would mean that I could test my code remotely every time I make an edit. It is really convenient since I'm already on remote. This makes testing and reediting really easy since all can be done in the terminal.

## Factors that might affect my decisions?
Some factors that might affect which method I choose might be if the task requires being run remotely or not, if the task requires being tested remotely than I might choose the second method, otherwise, I would go with the method I'm more familiar with: visual code studio. Another factor that might affect my decision is if I'm not just editing, but writting really long codes for the first time like maybe in programming assignments instead of just making minor edits. I would prefer VS code since they have tools that checks error and extensions that help make coding easier that vim doesn't have. And since I used VS code more, it is easier for me to use VS code. 