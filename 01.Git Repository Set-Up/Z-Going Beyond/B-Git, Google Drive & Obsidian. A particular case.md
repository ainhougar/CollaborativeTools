
Git & Google Drive both store content to a cloud that can be accessed from anywhere. A difference is that Google Drive can automatically synch files (with Google Drive Desktop & by storing files into its folders) whereas Git demands 3 action steps to update changes (add, commit, push). 

Initially, I was using Google Drive to synch my Obsidian Vaults, which allowed me to work on documents from multiple devices. After investigating the functionalities of Git, I have understood that storing my Obsidian Vault in GitHub is an alternative that works equally well. 

Nonetheless, what it harder to put in place is to keep Obsidian with Google Drive synching, as well as in GitHub. Google Drive synching creates configuration files within the synched folder that corrupt Git synching procedures. The configuration files contaminate all folders (user's working folders & .git folder containing all files that track GitHub synching). With .gitignore the configuration files can be ignored form working folders BUT not from the .git folder. 

-->  **This means that a .git folder cannot be stored in the Google Drive synched folder. There is no way it can be kept clean in this location.** 

--->  **A workaround is store the .git folder locally & set-up a *WorkTree* that tells Git to use the local .git folder to synch changes in Google Drive into the GitHub server** 

### Set-up a WorkTree

A worktree will **clone a directory from GitHub** in my local machine **while specifying more than 1 directory**. To fulfill the described scenario's interest, 
- the **first directory will be for the .git folder**(with all git synching configuration files) &
- the **second for the working files in google drive desktop**. 
This tells GitHub to use both directories when synching. We use the command lines & **git clone** **separate-git-dir** . 

git clone --separate-git-dir="C:/Users/AinhoaU/Documents/Repositories/CollaborationTools.git" \
  https://github.com/yourusername/CollaborationTools.git \
  "G:/My Drive/WORK/INGENIEUR/2-OTHER_WORK/1-RESSOURCES/CollaborationTools"

In the cloning process Git **uses a folder** where it deploys the "downloaded" documents & **creates a .git folder**. For proper cloning, we need: 
- Have the folder for deployment empty
- The .git folder must not already exist 


**A pre-requisite to setting up the WorkTree.**
- The repository must exist in GitHub 
	- Can be an empty repository (if set-up at initial work stages)
	- If already have a working folder, must: 
		- 1: Upload files to GitHub from the local machine (if files were in Google Drive, move them to the local machine. This way not uploading corrupted configuration files). 
		- 2. Choose the folder were files will be cloned  (i.e: the Google Drive folder. Ensure to have copy pasted it contents somewhere else for backup)