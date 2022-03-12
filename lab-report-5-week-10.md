# Lab-report-5-week-10



### Choose any two tests from the 652 commonmark-spec tests where your implementation 
### had different answers than the implementation we provided for lab 9.

The tests with different answers should correspond to **different bugs** 

* How you found the tests with different results (Did you use diff on the results of running a bash for loop? Did you search through manually? 
* Did you use some other programmatic idea?)

For each test:
* Describe which implementation is correct, or if you think neither is correct, by showing both actual outputs and indicating what the expected output is.
* For the implementation that’s not correct (or choose one if both are incorrect), describe the _bug (the problem in the code). 
* You don’t have to provide a fix, but you should be specific about what is wrong with the program, and show the code that should be fixed.



![Screenshot 2022-03-11 174254](https://user-images.githubusercontent.com/61016872/157998773-25346cfa-184b-4f14-ac00-c2a00ac68812.png)

running diff on the two results.txt output redirection that I have done



![Screenshot 2022-03-11 174232](https://user-images.githubusercontent.com/61016872/157998784-39071f3d-c63e-4fd4-9408-17c177901214.png)

On line 599 in results.txt there is difference, which corresponds to 342.md in the test files.

**342.md**

![Screenshot 2022-03-11 193116](https://user-images.githubusercontent.com/61016872/158002114-763e3f4c-6f42-4d9f-8069-ba86d1220996.png)




I believe that the implementation that the lab 9 Joe had for his ucsd-cse-15l-markdown-parse was the correct implementation.
The expected output is (/foo`) because the open closed bracket are found, and on my implementation it was somewhat right, but I had too many repeated (/foo`)
which is certainly not the expected output. I think the bug is it repeats the link too many times, which is not the expected behavior in this case.
In line 45 and 46, there is a counterbreak that keeps incrementing until 20, and it breaks afterwards so the while loop stops. I think what is happening is that
counterbreak shoud only run once to provide a valid output.


![Screenshot 2022-03-11 174426](https://user-images.githubusercontent.com/61016872/157998823-3e11db61-c84f-4ab2-a81b-e951c975bde8.png)

On line 1027 in results.txt, there is a difference, which corresponds to 508.md in test-files.

**508.md**

![Screenshot 2022-03-11 193249](https://user-images.githubusercontent.com/61016872/158002138-c7442390-31dd-4794-86f8-c72f0a6942ea.png)

I think in this case both my implementation and the professor's implementation is wrong. In the case of my implementation, I have repeated the same output too many times
as the expected behavior is a valid link with a single line of link inside the parentheses. It is a valid link, with escape sign right after the parentheses, so the escape sign
as well as other url would be printed in this case. For me, I would have to stop incrementing the counter and stop it at 1 before it prints out too many values of
repeated words, For the professor's implementation, the output is an empty link. so what should be done is to check the 
escape sign after parentheses and continue and add the link in the case.



## Danke!













