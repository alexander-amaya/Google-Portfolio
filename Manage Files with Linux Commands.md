# Manage Files with Linux Commands 

<br></br>
## Scenario

In this scenario, you need to ensure that the /home/analyst directory is properly organized.

You have to make a few changes to the /home/analyst directory and the files it contains.

You also have to edit a file to record the changes or updates you make to the directory.

Note: The lab starts with your user account, called analyst, already logged in to a Bash shell. This means you can start with the tasks as soon as you click the Start Lab button.
When you start, the /home/analyst directory contains the following subdirectories and files:

home
└── analyst
    ├── notes
    │   ├── Q3patches.txt
    │   └── tempnotes.txt
    ├── reports
    │   ├── Q1patches.txt
    │   └── Q2patches.txt
    └── temp
You need to modify the /home/analyst directory to the following directory and file structure:

home
└── analyst
    ├── logs
    ├── notes
    │   └── tasks.txt    
    └── reports
        ├── Q1patches.txt
        └── Q2patches.txt
        └── Q3patches.txt
Here’s how you’ll do this: First, you’ll create a new subdirectory called logs in the /home/analyst directory. Next, you’ll remove the temp subdirectory. Then, you’ll move the Q3patches.txt file to the reports subdirectory and delete the tempnotes.txt file. Finally, you’ll create a new .txt file called tasks in the notes subdirectory and add a note to the file describing the tasks you've performed.


## Response

