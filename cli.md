## Command Line

+ ```clear```: clear the terminal window of all text
+ ```ctrl+L```: clear the previous terminal data
+ ```pwd ```: print working directory
+ ```mkdir```: make directory
+ ```ls```: list contents of directory
+ ```touch filename```: create a file
+ ```rm filename```: permanently delete a file
+ ```rmdir foldername```: permanently delete a folder - cannot use if directory contains any files
+ ```rm -rf foldername```: this will permanently delete the folder with all files in there. The ```-rf``` are options, or flags, which we can pass to tell the command what to do. In this case the ```r``` tells the command ```(rm)``` to recursively remove the directory and its contents and the ```f``` forces the command to execute without a prompt and ignoring any warnings that are encountered.
+ ```cd```: change directory
  + ```cd directoryName```: change directory to directoryName; can also directly type the path ```cd documents/work/projects)```.
  + ```cd ..```: go back up one level
  + ```cd ~```: go back to home directory (Users/userName in Mac)
+ ```cp fileName newFileName```: copy the file and rename it in the same folder.
+ ```mv fileName /path-to-folder/```: move the file from one folder to another folder.

---
### Resources
+ [Basic Linux Navigation and File Management](https://www.digitalocean.com/community/tutorials/basic-linux-navigation-and-file-management)
+ [Learning the Shell](http://linuxcommand.org/lc3_learning_the_shell.php)
