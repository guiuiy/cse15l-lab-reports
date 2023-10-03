## Lab Report 1
---
# cd
1. When I used the cd command without any arguments, it kept me in the same directory I was in which was not an error.
   ```
   [user@sahara ~]$ cd
   [user@sahara ~]$
   ```
2. When I used the cd command with a directory as the argument, it brought me into the directory that I specified which was not an error.
   ```
   [user@sahara ~]$ cd lecture1
   [user@sahara ~/lecture1]$
   ```
3. When I used the cd command with a file as the argument, the terminal gave an error that said the file was not a directory.
   ```
   [user@sahara ~/lecture1]$ cd messages
   [user@sahara ~/lecture1/messages]$ cd no.txt
   bash: cd: no.txt: Not a directory
   ```
---
# ls
1. When I used the ls command without any arguments, it showed me the contents of the directory that I was in which is not an error.
   ```
   [user@sahara ~]$ ls
   **lecture1**
   ```
2. When I used the ls command with a directory as the argument, it showed me the contents of the directory that I specified only if the directory was inside the directory I was in. If the directory was not, it gave me an error.
   ```
   [user@sahara ~]$ ls lecture1
   Hello.class  Hello.java  **messages**  README
   [user@sahara ~]$ ls messages
   ls: cannot access 'messages': No such file or directory
   [user@sahara ~]$ cd lecture1
   [user@sahara ~/lecture1]$ ls messages
   en-us.txt  es-mx.txt  no.txt  zh-cn.txt
   ```
3. When I used the ls command with a file as the argument, it showed me the name of the file of the file that I specified only if the file was inside the directory I was in. If the file was not, it gave me an error.
   ```
   [user@sahara ~/lecture1]$ ls no.txt
   ls: cannot access 'no.txt': No such file or directory
   [user@sahara ~/lecture1]$ cd messages
   [user@sahara ~/lecture1/messages]$ ls no.txt
   no.txt
   ```
---
