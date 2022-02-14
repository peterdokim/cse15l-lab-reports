
# Lab-report3-week6 Writeup

## copying whole directory into the ieng6 account
### 1. Copying your whole markdown-parse directory to your ieng6 account
![Screenshot 2022-02-11 144054](https://user-images.githubusercontent.com/61016872/153680509-056db363-ef69-414e-b31f-afc2ae47fadf.png)

The -r option tells scp to work recursively. The . is the source, and is the current directory.</br>
The ~/markdown-parse tells scp to create the markdown-parse directory on the remote server (if it doesn’t exist),</br> 
and then copy the contents of this directory recursively there.

### 2. logging into your ieng6 account after doing this and compiling and running the tests for your repository

  I logged into my ieng6 account
![Screenshot 2022-02-11 144422](https://user-images.githubusercontent.com/61016872/153680776-99d3fb1b-7108-4ee5-9555-04dd78503819.png)

  Compile and run the test
  
![Screenshot 2022-02-11 144620](https://user-images.githubusercontent.com/61016872/153680946-52a81e5f-d538-4ea3-a44e-355d89934406.png)

This would run the test exactly like in our directory. so all our tests pass in this markdownparse test and markdownparse.java.

### 3. combining scp, ;, and ssh to copy the whole directory and run the tests in one line.


![Screenshot 2022-02-13 204010](https://user-images.githubusercontent.com/61016872/153801106-30b793b2-c207-4236-bca5-13d0e16558d3.png)


![Screenshot 2022-02-13 204055](https://user-images.githubusercontent.com/61016872/153801161-a6df2ca3-f3ce-469a-9e73-57eabeb53402.png)

After so many tries, I am glad that now it works. so we are copying the whole directory from our source directory to the server computer, or ieng6 computer for it to run in the server. scp -r copies recursively, logging into our account with ssh, and using quotes to list out the command we would like to test out for in the linux systems!







