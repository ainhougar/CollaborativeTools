
## Using .gitignore 

**Working across systems** 

Software systems create **configuration files** (cache etc) that support processing of the manually created files. Softwares may not always use configuration files that run in the background. Scenarios when they are required include third-party applications accessing/operating on files such as, Google Drive Synching. 

When these configuration files are created, we note that they are **specific to operating systems (Windows VS MacOs**; they also follow different file extension nomenclature. 
- Windows creates files with **".ini" extensions** & 
- MacOs creates files with the **".DS_Store"** extension. 

In order to **push/pull a repository that undergoes third-party operations on different system softwares** (i.e: Two individuals have enabled Google Synching of repository on different System softwares **-not the best example however-**), we will have to indicate GitHub specific configuration files that would ran into conflicts when pushing/pulling. We will identify these files by their extensions (among probably other features). Then, we will create a ".gitignore" note file, where we will specify that these files need to be ignored in the Git committing process. We can write something like this:

![[Screenshot 2025-06-26 161225 1.png]]


**When to set up .gitignore** 

.gitignore should be set up **before the first push is performed, ideally**. This way, the files that we do not wish to upload into GitHub, will never be uploaded there. This will prevent running into problems down the line. Some of these problems include: 
- **File conflicts** if working from different software systems that create different configuration files
- When pushing from a version that includes less files than the version on the Hub (ignores files with .gitignore), **the push will be blocked**. It will recommend that you pull the version from the Hub. GitHub understands the Hub repository version to be more complete and therefore the latest.  However, in this scenario (removing files that should have been ignored), we want to keep the changes in our local disk. There are two ways to go about this: 
	- Remove the files that are now ignored from GitHub (manually or in gitBash: `git rm -r --cached [file_name]`) & then push changes (**this step will no longer be blocked.**)
	- Force a push into GitHub `git push --force