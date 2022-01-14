# Hello. I am Do heon Kim
## Let's learn about how to install VSCODE!

### TOPIC : Remote Access

**## PART 1-Installing VSCODE**


![VSCODE](https://user-images.githubusercontent.com/61016872/149587319-e5ae0f5d-7636-4dca-9541-53640c1263cf.png)

Go to visual studio code website [https://code.visualstudio.com/](https://code.visualstudio.com/) and install it on your browser.
The return value should be presented on your screen like this(**Though this step is a bit further than for now**).


**## PART 2-Remotely Connecting**

1. Install OpenSSH.
2. lookup your course specific account(CSE 15L) from this website [https://sdacs.ucsd.edu/~icc/index.php]
3. Connect to the remote computer using VSCode Remote Option

The resulting output should look something like this. (*remember that acv has to be changed to your own account*)
Give your password for the account after you press 'Yes' for the first time.


![Output](https://user-images.githubusercontent.com/61016872/149592063-d4e686e9-3b3e-474a-b87a-68065f42d0aa.png)

**## Part 3-Try some commands**

'try some commands such as cd,ls, pwd,mkdir, cp'

![Initial workings](https://user-images.githubusercontent.com/61016872/149595269-65af3a17-79fc-474a-849b-df244366fab6.png)

![trying out commands](https://user-images.githubusercontent.com/61016872/149593285-e67dc205-6d9f-4ffd-b5e6-3ae3048bdd1f.png)




Some notes to go through
- cannot access someone else's folder, can only access my folder
-  ls just list one file, but ls -lat or ls -a list all the files inside the server computer
-  cd is change directory, can go up directory by implementing 'cd ..'
-  cp would be copying files to a directory, cat command read data from file and print output [Basic command line words](https://www.codecademy.com/article/command-line-commands)

**## Part 4-Moving files over SSH with 'scp'**

### We would now like to copy files back and forth between client and server computers.

1. Create a file called WhereAmI.java in your client computer where you put following content into it. 

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

run javac and java command and note down what you observe.

2. Now run following command

```
scp WhereAmI.java cs15lwi22acv@ieng6.ucsd.edu:~/
```


![listing files](https://user-images.githubusercontent.com/61016872/149594901-1c39d0ba-2843-4a49-a91f-7d029b0843d1.png)

You can now see that beside the perl5 orignal file, whereAmI.java has also been implemented.

note that system.getproperty would prompt a property of the machine it is run from. so depending on where you work(client or server),<br>
its property would be different

**## Part 5 -Setting an SSH key**

Everytime we login to ssh, and scp files, we have to type our password. A good way that could get rid of this is<br>
use  **SSH KEYS**.


![SSH KEYGEN](https://user-images.githubusercontent.com/61016872/149595509-304b2d04-4076-4859-ac24-e8297e9e9ffe.png)


**ON Windows, extra step is described in the document link below**
<br> [SSH-ADD Steps for Windows](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)
*Now this would create public and private key stored in your computer*

now copy your public key to server client of my user-account.
```
$ ssh cs15lwi22acv@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
# back on client
$ scp /Users/peter/.ssh/id_rsa.pub cs15lwi22@ieng6.ucsd.edu:~/.ssh/authorized_keys
# You use your username and the path you saw in the command above
```

Command line output would look something like this.

(After you do this, you could always scp or ssh from your computer to server computer without password 
<br> entering every time)

**## Part 6- Optimizing Remote Running**

Now you can make local edits to your whereAmI.java in your computer(client),
<br> and copy into remote server to run it there.

```
$ ssh cs15lwi22@ieng6.ucsd.edu "ls"
$ scp WhereAmI.java cs15lwi22acv@ieng6.ucsd.edu:~/ ; ssh cs15lwi22acv@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI"
$ ssh cs15lwi22@ieng6.ucsd.edu "ls -lat"
$ ssh cs15lwi22@ieng6.ucsd.edu "pwd"

```

By trying some of these commands we know that the commands could be run from your computer to the remote server,
<br> without having to login to the server everytime writing passwords.(**Incredibly useful**)




![remote command operations](https://user-images.githubusercontent.com/61016872/149596794-c1ab5eaf-e82b-4d3a-8547-9f5fbd2fdd69.png)




