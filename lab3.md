**Part 1**

This is the code I used to write StringServer

![image](https://user-images.githubusercontent.com/130091977/234189390-64d49b60-4c4c-4693-ba25-72e725b757f5.png)


![image](https://user-images.githubusercontent.com/130091977/234189615-bec9eafe-82c2-4568-9352-398651974e09.png)

Handle request is called 5 times in this code. The first call returns an empty string, and the other 4 append the query plus a newline character after it. "Hello" is called upon 3 times and appended to the website, then "How are you" is added. After each url is inputted, the value of str gets longer and longer

![image](https://user-images.githubusercontent.com/130091977/234190060-abb8027c-9416-43a8-8f87-9568747f6b0e.png)

This screenshot is the same, except Handle request is called a 6th time, adding "googoogaga" plus a newline character after it. str is once again added to.


**Part 2**

I'll be using reverseInPlace as the method to focus Part 2 of my lab report on.

Failure-inducing input: 

    {3,4}

Input that does not induce a failure:

    {3}
    
The symptom of running the tests(and the actual tests):

![image](https://user-images.githubusercontent.com/130091977/234192946-7d4e5ac8-d498-4d3b-8bf6-a63fa6e83afd.png)

Code Pre-fix:
`
    int[] copy = new int[arr.length];
    for(int i = 0; i < arr.length; i++) {
      copy[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i++){
      arr[i] = copy[arr.length - 1 - i];
    }
  }
 `


