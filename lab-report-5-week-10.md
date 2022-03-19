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



<img src="https://user-images.githubusercontent.com/61016872/157998773-25346cfa-184b-4f14-ac00-c2a00ac68812.png" width="800">


# Test 1
## running diff on the two results.txt output redirection that I have done

<img src="https://user-images.githubusercontent.com/61016872/157998784-39071f3d-c63e-4fd4-9408-17c177901214.png" width="3000" height="200">
First output is my markdownparse file result, second output is professor's markdownparse file result for 342.md test file

**Both Actual Outputs are shown here using diff**

On line 599 in results.txt there is difference, which corresponds to 342.md in the test files.



### Test 1 actual file 342.md
<img src="https://user-images.githubusercontent.com/61016872/158002114-763e3f4c-6f42-4d9f-8069-ba86d1220996.png" width="2000" height="200">

**Expected output []**

I do not think that both the actual output is the expected output. There is a backtick within the link representation, so the file
I think the bug is it repeats the link too many times, which is not the expected behavior in this case. Also bug in professor's case is that it prints an
output inside the link, which should not be happening. The file says it is not an link, which is not a link because of the backtick that is within the open and
closed bracket which would have to evaluate string or some form of command in this case, so we could say that this is wrong.

# Test 2

## running diff on the two results.txt output redirection

**These are the actual outputs to the test 2**
<img src="https://user-images.githubusercontent.com/61016872/157998823-3e11db61-c84f-4ab2-a81b-e951c975bde8.png" width="1000" height="200">
First output is my markdownparse.java file result, and Second output is the professor's markdownparse.java result

On line 1027 in results.txt, there is a difference, which corresponds to 508.md in test-files



### Test 2 actual file 508.md
<img src="https://user-images.githubusercontent.com/61016872/158002138-c7442390-31dd-4794-86f8-c72f0a6942ea.png" width="1000" height="100">

-Expected output [/url 'title "and" title'] </br>

I think in this case both my implementation and the professor's implementation is wrong. In the case of my implementation, I have repeated the same output too many times
as the expected behavior is a valid link with a single line of link inside the parentheses. It is a valid link, with escape sign right after the parentheses, so the escape sign
as well as other url would be printed in this case. For me, I would have to stop incrementing the counter and stop it at 1 before it prints out too many values of
repeated words, For the professor's implementation, the output is an empty link. so what should be done is to check the 
escape sign after parentheses and continue and add the link in the case.
















