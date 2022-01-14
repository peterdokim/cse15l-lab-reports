# Hello. I am Do heon Kim
## Let's learn about how to install VSCODE!

### TOPIC : Remote Access

**PART 1-Installing VSCODE**


![VSCODE](https://user-images.githubusercontent.com/61016872/149587319-e5ae0f5d-7636-4dca-9541-53640c1263cf.png)

Go to visual studio code website [https://code.visualstudio.com/](https://code.visualstudio.com/) and install it on your browser.
The return value should be presented on your screen like this(**Though this step is a bit further than for now**).


**PART 2-Remotely Connecting**

1. Install OpenSSH.
2. lookup your course specific account(CSE 15L) from this website [https://sdacs.ucsd.edu/~icc/index.php]
3. Connect to the remote computer using VSCode Remote Option

The resulting output should look something like this. (*remember that acv has to be changed to your own account*)
Give your password for the account after you press 'Yes' for the first time.


![Output](https://user-images.githubusercontent.com/61016872/149592063-d4e686e9-3b3e-474a-b87a-68065f42d0aa.png)

**Part 3-Try some commands**

'try some commands such as cd,ls, pwd,mkdir, cp'

![trying out commands](https://user-images.githubusercontent.com/61016872/149593285-e67dc205-6d9f-4ffd-b5e6-3ae3048bdd1f.png)



Some notes to go through
- cannot access someone else's folder, can only access my folder
-  ls just list one file, but ls -lat or ls -a list all the files inside the server computer
-  cd is change directory, can go up directory by implementing 'cd ..'
-  cp would be copying files to a directory, cat command read data from file and print output [Basic command line words](https://www.codecademy.com/article/command-line-commands)

**Part 4-Moving files over SSH with 'scp'**

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













