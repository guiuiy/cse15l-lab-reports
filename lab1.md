# Lab Report 1
---
## cd
1. When I used the `cd` command without any arguments, if I was in the home directory, it kept me in the same directory, but if I was in another directory other than home, I would go to home. Not an error.
   
      Working directory: `/home`
      ```
      [user@sahara ~]$ cd
      [user@sahara ~]$
      ```
      Working directory: `/home/lecture1`
      ```
      [user@sahara ~/lecture1]$ cd
      [user@sahara ~]$
      ```
      Working directory `/home/lecture1/messages`
      ```
      [user@sahara ~/lecture1/messages]$ cd
      [user@sahara ~]$
      ```
   
2. When I used the `cd` command with a relative path or an absolute path to a directory as the argument, it brought me into the directory that I specified which is not an error.

      Working directory: `/home`
      ```
      [user@sahara ~]$ cd lecture1/messages
      [user@sahara ~/lecture1/messages]$
      ``` 
      Working directory: `/home/lecture1`
      ```
      [user@sahara ~/lecture1]$ cd messages
      [user@sahara ~/lecture1/messages]$
      ```
      Working directory: `/home`
      ```
      [user@sahara ~]$ cd /home/lecture1/messages
      [user@sahara ~/lecture1/messages]$
      ```
   
3. When I used the `cd` command with a file as the argument, the terminal said the file was not a directory which is not an error.

      Working directory: `/home/lecture1/messages`
      ```
      [user@sahara ~/lecture1/messages]$ cd no.txt
      bash: cd: no.txt: Not a directory
      ```
---

## ls
1. When I used the `ls` command without any arguments, it showed me the directories and files in the directory that I was in which is not an error.

      Working directory: `/home`
      ```
      [user@sahara ~]$ ls
      **lecture1**
      ```
      Working directory: `/home/lecture1`
      ```
      [user@sahara ~/lecture1]$ ls
      Hello.class  Hello.java  **messages**  README
      ```
2. When I used the `ls` command with a directory as the argument, it showed me the directories and files in the directory that I specified only if the directory was inside the directory I was in. If the directory was not, I needed to give it a proper relative path or it would say that it cannot access the directory, error.

      Working directory: `/home`
      ```
      [user@sahara ~]$ ls lecture1
      Hello.class  Hello.java  **messages**  README
      [user@sahara ~]$ ls messages
      ls: cannot access 'messages': No such file or directory
      [user@sahara ~]$ ls lecture1/messages
      en-us.txt  es-mx.txt  no.txt  zh-cn.txt
      ```
3. When I used the `ls` command with a file as the argument, it showed me the relative path I passed that I specified only if the file was inside the directory I was in. If the file was not, I needed to give it a proper relative path or it it would say that it cannot access the file, error.

      Working directory: `/home/lecture1`
      ```
      [user@sahara ~/lecture1]$ ls no.txt
      ls: cannot access 'no.txt': No such file or directory
      [user@sahara ~/lecture1]$ ls messages/no.txt
      messages/no.txt
      ```
      Working directory: `/home/lecture1/messages`
      ```
      [user@sahara ~/lecture1/messages]$ ls no.txt
      no.txt
      ```
---

## cat
1. When I used the `cat` command without any arguments, nothing appeared after the command. Providing input would repeat the input in the next line. This may or may not be an error.

      Working directory: `/home`
      ```
      [user@sahara ~]$ cat
      aa
      aa
      hello
      hello
      ```
2. When I used the `cat` command with a directory as the argument, it outputted that the directory "Is a directory". This is not an error

      Working directory: `/home`
      ```
      [user@sahara ~]$ cat lecture1
      cat: lecture1: Is a directory
      [user@sahara ~]$ cat lecture1/messages
      cat: lecture1/messages: Is a directory
      ```
3. When I used the `cat` command with a file as the argument, it outputted the data in the file if the file was in the working directory. If the file was not in the directory, it will say that there is no such file or directory, error.

      Working directory: `/home`
      ```
      [user@sahara ~]$ cat no.txt
      cat: no.txt: No such file or directory
      ```
      Working directory: `/home/lecture1/messages`
      ```
      [user@sahara ~lecture1/messages]$ cat no.txt
      Hei Verden!
      ```
---

[HOME](https://guiuiy.github.io/cse15l-lab-reports/)
