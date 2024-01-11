# Lab Report 1
## Remote System and FileSystem

This week, we learnt about the basic filesystem commands, including **cd**, **ls**, and **cat**.
In the following, we will be showing examples of using each command with *no* argument, with a path to a *directory* as an argument, and with a path to a *file* as an argument. 
The demonstrations will be shown in the following workspace: [link](https://edstem.org/us/courses/51148/workspaces/potvx6SYlBTZfdQa0SO0soDHoPkfwHEa).

The organization of the files in our demo is shown in the image below:

![image](https://github.com/mfzzm33/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-11%20at%209.17.20%20AM.png)

Execute the **cd** command:
```
[user@sahara ~]$ cd
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ cd README
bash: cd: README: Not a directory
```
1. When there's no arguments after, nothing happens. 
2. When the argument is a path to a directory, it will change the working directory to `/lecture1`.
3. When the argument is a path to a file, it creates an **error** and returns that the file is not a directory.
4. The working directory of the first two commands are in `/home` while the working directory of the last is in `lecture1`. This is because we changed the working directory into lecture1 in the last command.
***
Execute the **ls** command:
```
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
[user@sahara ~]$ ls README
ls: cannot access 'README': No such file or directory
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ ls README
README
```
1. We first set the working directory at `/home`. When there's no arguments after, it returns the only directory *lecture1* under it. 
2. When the argument is a path to a directory, it lists all the files in the directory `/lecture1`.
3. When the argument is a path to a file, it creates an **error** since it cannot directly access the file in the directory lecture1. So we change the working directory to *lecture1* and redo the command, then it returns the name of the file itself.
4. The working directory of the first three commands are in `/home` while the working directory of the last is in `lecture1`.
***
Execute the **cat** command:
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }[user@sahara ~/lecture1]$ cat
Hello world!
Hello world!
```
1. When there's no arguments after, the terminal will start copying whatever I wrote down. 
2. When the argument is a path to a directory, it creates an **error**, suggesting it cannot connect to a directory.
3. When the argument is a path to a file,  it prints the content in the file.
4. The working directory of the first two commands are in `/home` while the working directory of the last is in `lecture1`.
