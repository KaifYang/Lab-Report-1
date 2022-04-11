# ieng6 login tutorial

## Installing VScode

1. Search for VSCode on any search engines.
2. Download and setup VSCode.
***
**The front page of VSCode when successfully setted up**

![The front page of VSCode when successfully setted up](https://github.com/KaifYang/Lab-Report-1/blob/main/vscode.png)
***

## Remotely Connecting

1. Open a new terminal in VSCode
2. enter command(xx means the unique characters of yours)
```
ssh cs15lsp22xx@ieng6.ucsd.edu
```
3. enter password after [resetting](https://cdn-uploads.piazza.com/paste/ktv2gnof3sx5bf/181c3cb053df5cf1ccaf0457f56f12a2e5aa90b139aef8c2ea8fcc590f02fadf/How-to-Reset-your-Password.pdf) to connect to server

***
**This image shows what happens after your are successfully connected to the server.**

![Terminal after connection](https://github.com/KaifYang/Lab-Report-1/blob/main/login.png)
***


## Trying Some Commands

* Try running the commands cd, ls, pwd, mkdir, and cp on the terminal after login.
* [Here is a website with other basic commands you can try](https://phoenixnap.com/kb/linux-ssh-commands)
***
**Some examples**

![Some examples](https://github.com/KaifYang/Lab-Report-1/blob/main/try%20some%20commands.png)
***

## Moving Files with scp

1. Copy this code and create a new local file in your computer
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
2. Run this command in the terminal(xx means the unique characters of yours):
```
scp WhereAmI.java cs15lsp22xx@ieng6.ucsd.edu:~/
```
3. Enter the password
4. Log into ieng6 with ssh again. Use ls to check if the file is in the home directory.
***
**Here is the whole process of using scp and ssh**

![image](https://github.com/KaifYang/Lab-Report-1/blob/main/copy%20file.png)
***
## Setting an SSH Key

1. Use the command `ssh-keygen` to generate a key. (Use `ssh-keygen -t ed25519` instead if you are using windows system)
2. Then follow this process:
```
$ ssh cs15lsp22zz@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
# back on client
$ scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys
# You use your username and the path you saw in the command above
```
3. Then you can login the server without password using ssh or scp.
***
**This is how loging in looks like if the key setup is successful**

![image](https://github.com/KaifYang/Lab-Report-1/blob/main/without%20pass.png)
***
## Optimizing Remote Running

To increase the speed of uploading your edits of local file to the server, you can do these things:
1. You can write the command in quotes at the end of your ssh command to directly run it on the remote server.
2. You can write several commands in the same line
3. You can use up arrow to recall the last command you run.

Combine them together, you are able to directly run the new edition of the WhereAmI.java file on the server in one line. You can update the file and run the file in two lines.
***
**The image of running the file in one line**

![image](https://github.com/KaifYang/Lab-Report-1/blob/main/running%20WAI.png)


