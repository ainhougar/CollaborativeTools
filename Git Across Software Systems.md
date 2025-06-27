

## Using .gitignore 

**Working across systems** 

Software systems create **configuration files** (cache etc) that support processing of the files that we created. These configuration files are **specific to operating systems**; they also follow different file extension nomenclature. 
- Windows creates files with **".ini" extensions** & 
- MacOs creates files with the **".DS_Store"** extension. 

In order to **push/pull across system software**, we will have to indicate GitHub to ignore files with these extensions. For that, we create a ".gitignore" note file, where we specify that these files need to be ignored in the throughout the file cloning operation. We can write something like this:

![[Screenshot 2025-06-26 161225 1.png]]


**When to set up .gitignore** 
