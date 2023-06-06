# **Edsteam Conversation**
## Original Post

**What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?**

Hp laptop, windows, VSCode with Git Bash terminal. I'm attempting to run a bash file.

**Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.**

![image](https://github.com/beachu23/cse15l-lab-reports/assets/130091977/6cf9815a-2ab7-4d72-a4fe-584900675cec)

My bash script which I'm using to run my rps game doesn't work. I tried to run it with the -Xlint and -g option for debugging purposes, and I expected to see the location of the code that produced the warning as well as more information on what caused the warning. 

**Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.**

My bash script is the following: 

![image](https://github.com/beachu23/cse15l-lab-reports/assets/130091977/ab44f9fc-fd76-4c66-b920-157e9cebda6b)

The commands I typed are:

```chmod +x rps.sh```
```./rps.sh```

The bash script is in the same folder as the java file and I'm in the correct directory. I compiled the java file and ran it without the bash script once normally, and once using -Xlint: unchecked previously. I have not run any other commands in the terminal.
