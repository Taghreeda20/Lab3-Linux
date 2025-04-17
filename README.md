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

    
• What is the maximum permission a file can have, by default when it is just created? And what is that for directory. 666 read write not excute. (file) 777 read write and excute (Dir) • Change your default permissions to be no permission to everyone then create a directory and a file to verify






