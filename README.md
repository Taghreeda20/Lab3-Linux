# Lab3-Linux
1- Create a user account with the following attribute
• username: “your first name” 
• Fullname/comment: “full name” 
• Password: islam : 

    sudo useradd Taghreed -c "Taghreed Abdulbassit" -m -p islam

2- Create a user account with the following attribute 
• Username: baduser 
• Full name/comment: Bad User
• Password: baduser : 

    sudo useradd baduser -c "Bad User" -m -p baduser

3- Create a supplementary (Secondary) group called pgroup with group ID of 30000 : 

    sudo groupadd -g 30000 pgroup

4- Create a supplementary group called badgroup : 

    sudo groupadd badgroup

5- Add islam user to the pgroup group as a supplementary group : 

    sudo usermod -aG pgroup Taghreed

6- Modify the password of islam's account to password : 

    sudo passwd Taghreed

7- Modify islam's account so the password expires after 30 days : 

    sudo chage -M 30 Taghreed

8- Lock bad user account so he can't log in : 

    sudo passwd -l baduser

9- Delete bad user account : 

    sudo userdel -rf baduser

10- Delete the supplementary group called badgroup : 

    sudo groupdel badgroup

11- Create a folder called myteam in your home directory and change its permissions to read only for the owner :

    mkdir ~/myteam
    chmod 400 ~/myteam

12- Using the command Line 

• Change the permissions of oldpasswd file to give owner read and write permissions and for group write and execute and execute only for the others: 

    sudo chmod u=rw,g=wx,o=x oldpasswd
    sudo chmod 631 oldpasswd
    
• Change your default permissions to be as above : 

    umask 026
    echo "umask 026" >> ~/.bashrc
    touch testfile
    mkdir testdir
    ls -l testfile
    ls -ld testdir
    
• What is the maximum permission a file can have, by default when it is just created? And what is that for directory? 666 for files (read & write not excute ) And 777 for directories ( read write and excute) .

• Change your default permissions to be no permission to everyone then create a directory and a file to verify : 

     umask 777
     touch file25
     mkdir dir25
     ls -l file25
     s -ld dir25

 13- Starting from your home directory, find all files that were modified in the last two day : 

    sudo find ~ -type f -mtime -2

 14- Starting from /etc, find files owned by root user : 

    sudo find /etc -type f -user root

 15- Find all directories in your home directory : 

    sudo find ~ -type d

 16- Write a command to search for all files on the system that, its name is ".profile" : 

    sudo find / -name .profile

  17- Identify the file types of the following: /etc/passwd, /dev/pts/0, /etc, /dev/sda : 

    file /etc/passwd
    file /dev/pts/0
    file /etc
    file /dev/sda

18- List the inode numbers of /, /etc, /etc/hosts  : 

    ls -i /
    ls -i /etc
    ls -i /etc/hosts

19- Copy /etc/passwd to your home directory, use the commands diff and cmp, and Edit in the file you copied, and then use these commands again, and check the output : 

    cp /etc/passwd ~/passwd_copy
    diff /etc/passwd ~/passwd_copy
    cmp  /etc/passwd ~/passwd_copy
    nano ~/passwd_copy      # I add a comment to show the edit 
    diff /etc/passwd ~/passwd_copy
    cmp  /etc/passwd ~/passwd_copy

20- Create a symbolic link of /etc/passwd in /boot : 

    sudo ln -s /etc/passwd /boot/passwd_symlink

21-Create a hard link of /etc/passwd in /boot . Could you? Why?

    sudo ln /etc/passwd /boot/passwd_hardlink 
No,because hard links require the source (/etc/passwd) and destination (/boot) to be on the same filesystem.and /etc and /boot are typically on separate filesystems










