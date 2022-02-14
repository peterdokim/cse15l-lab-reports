
# Lab-report3-week6 Writeup

## copying whole directory into the ieng6 account
1. Copying your whole markdown-parse directory to your ieng6 account
![Screenshot 2022-02-11 144054](https://user-images.githubusercontent.com/61016872/153680509-056db363-ef69-414e-b31f-afc2ae47fadf.png)

The -r option tells scp to work recursively. The . is the source, and is the current directory.</br>
The ~/markdown-parse tells scp to create the markdown-parse directory on the remote server (if it doesn’t exist),</br> 
and then copy the contents of this directory recursively there.

2. logging into your ieng6 account after doing this and compiling and running the tests for your repository

  I logged into my ieng6 account
![Screenshot 2022-02-11 144422](https://user-images.githubusercontent.com/61016872/153680776-99d3fb1b-7108-4ee5-9555-04dd78503819.png)

  Compile and run the test
  
![Screenshot 2022-02-11 144620](https://user-images.githubusercontent.com/61016872/153680946-52a81e5f-d538-4ea3-a44e-355d89934406.png)

This would run the test exactly like in our directory. so all our tests pass in this markdownparse test and markdownparse.java.

3. combining scp, ;, and ssh to copy the whole directory and run the tests in one line.
![Screenshot 2022-02-13 162344](https://user-images.githubusercontent.com/61016872/153782121-687e61ce-e4f2-4025-aca4-9ad71407b9a0.png)

![Screenshot 2022-02-13 162419](https://user-images.githubusercontent.com/61016872/153782126-d3d0e092-caa6-4b01-b8a5-06c288f95659.png)


The copying logging into java is fine now, but the symbols are not recongnized as indicated by the diagram




