File permissions in Linux
Project description
(Portfolio Case Study)

In this project, I examined and modified Linux file and directory permissions to ensure that only authorized users had access to sensitive resources. I worked within a research team environment where improper permissions could expose confidential project files. Using Linux commands, I identified incorrect permissions and updated them to strengthen system security and enforce the principle of least privilege.
Check file and directory details
To check file and directory permissions, I used the following Linux command:
ls –la 

The ls -la command lists all files and directories in the current directory, including hidden files, along with detailed permission information. This output includes a 10-character permission string, ownership details, and file names. Using this command allowed me to identify which files had permissions that did not match organizational security requirements.
Describe the permissions string
The 10-character permissions string indicates the file type and the permissions assigned to the user, group, and other.
•	1st character: Indicates file type
o	- = regular file
o	d = directory
•	2nd–4th characters: User permissions (read, write, execute)
•	5th–7th characters: Group permissions (read, write, execute)
•	8th–10th characters: Other permissions (read, write, execute)
For example, the permission string -rw-rw-r-- means:
•	The item is a regular file
•	The user can read and write
•	The group can read and write
•	Others can read only

Change file permissions
The organization does not allow other users to have write access to any files. After reviewing the permissions, I determined that project_k.txt granted write permissions to other users.

To remove write permissions for other, I used the following command:
Chmod o-w project_k.txt

After running this command, I verified the changes using ls -la to ensure that other users no longer had write access.
Change file permissions on a hidden file
The hidden file .project_x.txt was archived and should not be writable by any users. However, the user and group should retain read access.

To update the permissions, I ran:
Chmod u-w,g-w,g+r .project_txt

This command removed write permissions from both the user and group and ensured the group retained read access. Hidden files are identified by a leading period (.) and can be viewed using the -a option with the ls command.
Change directory permissions
Only the researcher2 user should have access to the drafts directory and its contents. The group previously had execute permissions, which allowed access.

To correct this, I used:
Chmod g-x drafts

This command removed execute permissions from the group, ensuring that only the file owner could access the directory.
Summary
In this project, I used Linux commands to review and modify file and directory permissions within a research environment.
I identified files with unauthorized access and corrected them using the chmod command. By applying least-privilege principles and verifying changes with ls -la, 
I strengthened system security and ensured that only authorized users could access sensitive resources.

Linux file permissions case study

