# Linux Essentials for DevOps.

1. Print the present working directory.

![The Image show the present working directory](image/pwd.png)

2. Create a directory named 'advanced _directory or anything' and navigate into it.


3. Create two files, "file_a.txt" and "file_b.txt" in the linux_Essential directory and list them with detailed information.

- Run the commands below to create the two files.

` touch file_a.txt file_b.txt`

Run  `ls -l` to view the files and directories, detailed information including permissions, owner, file size, and modification date.

![The Image shows the creation of files and viewing the content](image/file-ab.png)


4. Create a symbolic link to "fila_a.txt" named "link_to_file_a" in the same directory.

Below is the command to create symbolic link in Linux.

`ln -s`

I have run `ln -s file_a.txt link_to_file_a` this create a symbolic link named `link_to_file_a` pointing to `file_a.txt` in the same directory.

![The Image shows the linking of a file](image/link-file.png)

5. Change the permissions of "file_b.txt" to make it readable, writable, but not executable by the owner, and read-only for others.

To execute this task `chmod` command to be used to change the permission of file `file_b.txt`.

Run the command below to execute.

`chmod 644 file_b.txt`

This set the permission as follows:

User Category       Permission                  Numeric Value

1. Owner        Read and write (`rw-`)              6

2. Group        Read only (`r--`)                   4

3. Others       Read only (`r--`)                   4

The owner does not have execute permission, and neither the group not other can write to or execute the file.

![The Image show the chmod file](image/chmod-file.png)

*********************************************************************************************************************

6. Create a new directory "nested_directory" and "present-working directory" and copy both file_a.txt and file_b.txt into it.

run `mkdir nested_directory`

Then, run `cp file_a.txt file_b.txt nested_directory/`

![The Image show the nested directory](image/nested-directory.png)


7. Navigate into "nested_directory" create a new file named "secret.txt" and write "Hello world!" into it use a single command.

![The Image show the creation of new files](image/nested-file.png).



8. Move `file_a.txt` and `file_b.txt` from "nested_directory" back to "present-working-directory" using one command.

Run the command below:

`mv nested_directory/file_a.txt nested_directory/file_b.txt .`

![The Image shows the nested directory file move back to .](image/nested_directory_file.png)


9. Return to "Linux-Essentials/Present working directory" and create a `.hidden_file.`

run: `touch .hidden_file`

![The Image shows the hidden file](image/hidden-file.png)


10. List all files (including hidden ones) in "present_working_directory" with human-readable file sizes.


![The Image shows all the files including hidden ones](image/list-files-hidden.png)

11. Create a new directory "backup" and archive("tar") all files in "Linux-Essential-for DevOps" (including hidden files) into "backup/archive.tar".

1. Create a directory called `backup`.
2. Take everything inside `Linux-Essentials-for DevOps`, including hidden files.
3. Put all of it into a TAR archive called `archive.tar`.
4. Store that archive inside `backup`.

Run:

`mkdir backup && tar -cvf backup/archive.tar -C "Linux-Essential-for-DevOps" .`

Let me break it down.

1. 