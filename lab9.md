# **Edsteam Conversation**
## Original Post

**What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?**

Hp laptop, windows, VSCode with Git Bash terminal. I'm attempting to run a bash file.

**Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.**

![image](https://github.com/beachu23/cse15l-lab-reports/assets/130091977/3cc96ffd-5ca3-42fc-97c4-bf5eac2c8b4d)

My bash script which I'm using to run my rps game doesn't work. I tried to run it with the -Xlint and -g option for debugging purposes, and I expected to see the location of the code that produced the warning as well as more information on what caused the warning. 

**Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.**

My bash script is the following: 

![image](https://github.com/beachu23/cse15l-lab-reports/assets/130091977/1f72f0a5-70f9-4031-be8f-c3b70fd203c6)

The commands I typed are:

```chmod +x rps.sh```

```./rps.sh```

The bash script is in the same folder as the java file and I'm in the correct directory. I compiled the java file and ran it without the bash script once normally, and once using -Xlint: unchecked previously. I have not run any other commands in the terminal.


## TA response
> hey!
> 
> I see a couple of errors in your input. You should read more on where to close the loop when an else statement is present(fi should be after the else statement concludes!) and when providing multiple flags, you should format them as an array–or else bash will not run all of them!.  Let me know if it works!

## Student response
![image](https://github.com/beachu23/cse15l-lab-reports/assets/130091977/ee1456da-3979-455b-b494-3ab291589388)

![image](https://github.com/beachu23/cse15l-lab-reports/assets/130091977/ff32d667-d57b-4016-9925-46ad781c6cd4)

thank you so much the fixes worked! 

## More information

I wrote the java code from scratch and it's saved in my home directory in a folder called cse15l. The bash script is saved at the same location, and is titled rps.sh. Below is a screenshot of the file structure(it's very simple):

![image](https://github.com/beachu23/cse15l-lab-reports/assets/130091977/e600114c-18f2-47ee-b4dd-76d6ba99a81d)

My code for my java file is:

```
import java.util.Random;

public class RockPaperScissors<T> {
    private T[] moves;

    public RockPaperScissors(T[] moves) {
        this.moves = moves;
    }

    public T getRandomMove() {
        Random random = new Random();
        int index = random.nextInt(moves.length);
        return moves[index];
    }

    public String play(T playerMove, T computerMove) {
        if (playerMove.equals(computerMove)) {
            return "It's a tie!";
        } else if (
            ((Comparable) playerMove).compareTo(computerMove) < 0 ||
            (playerMove.equals(moves[0]) && computerMove.equals(moves[moves.length - 1]))
        ) {
            return "Player wins!";
        } else {
            return "Computer wins!";
        }
    }

    public static void main(String[] args) {
        String[] moves = {"Rock", "Paper", "Scissors"};
        RockPaperScissors<String> game = new RockPaperScissors<>(moves);

        String playerMove = game.getRandomMove();
        String computerMove = game.getRandomMove();

        System.out.println("Player chose: " + playerMove);
        System.out.println("Computer chose: " + computerMove);

        String result = game.play(playerMove, computerMove);
        System.out.println("Result: " + result);
    }
}

```
I did not change the java file at any point during the process.

This is the original bash script before the changes:

```
java_file="RockPaperScissors.java"

compiler_flags= "-g" "-Xlint:unchecked"

javac "${compiler_flags[@]}" "$java_file"

if [[ $output =~ "error:" ]]; then
    echo "Compilation failed. Game cannot be run."
fi
else
    echo "Compilation successful. Running the game..."
    
    # Deliberate error: Missing command-line arguments
    java RockPaperScissors
```

This is the final bash script:

```
java_file="RockPaperScissors.java"

compiler_flags=(-g -Xlint:unchecked)

javac "${compiler_flags[@]}" "$java_file"

if [[ $output =~ "error:" ]]; then
    echo "Compilation failed. Game cannot be run."
else
    echo "Compilation successful. Running the game..."
    
    # Deliberate error: Missing command-line arguments
    java RockPaperScissors
fi
```







