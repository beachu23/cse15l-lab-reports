Today's lab will be focused on the command: ```grep```.

We will be examining 4 different ways to utilize this command. All commands will be run on the **technical** folder provided.

1. ```-e``` option

Input a:

```
grep -e "suicide" -e "temperate" 911report/chapter-1.txt
```

Output:
```
    Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania Avenue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.
the hijacking would take the traditional form: that is, it would not be a suicide hijacking designed to convert the aircraft into a guided missile.
```

Comments: The command allows ```grep``` to search for multiple string patterns in the file. If either pattern shows up in the file, the line will be included in the output. 

Input b:

```
grep -e "suicide"  911report/chapter-1.txt
```

Output: 

```
the hijacking would take the traditional form: that is, it would not be a suicide hijacking designed to convert the aircraft into a guided missile.
```

Comments: If only one string is passed to ```grep```, it will function as if the ```-e``` option does not exist. In other words, it will simply search for the one string presented.

Sources used: chatGPT

chatGPT prompt:

> give me an option with grep that can specify multiple patterns to match


chatGPT response:

> Certainly! To specify multiple patterns to match with grep, you can use the -e option. Here's an example:
> ``` 
> grep -e "pattern1" -e "pattern2" file.txt
> ```
> In this example, grep will search for lines that contain either "pattern1" or "pattern2" in the file file.txt. You can specify as many patterns as needed by 
> using multiple -e options followed by the respective pattern.
> 
> For instance, if you want to search for lines that contain either "apple," "banana," or "orange," you can use the following command:
> ```
> grep -e "apple" -e "banana" -e "orange" file.txt
> ```
> grep will display all lines from file.txt that match any of the specified patterns.


2. ```-c ``` option

Input a:

```
grep -c "suicide" 911report/chapter-1.txt 911report/chapter-2.txt
```

Output:

```
911report/chapter-1.txt:1
911report/chapter-2.txt:3
```

Comments: ```-c``` counts the number of lines where the text appears in the file. In the case of multiple files, it'll list the file relative path, as well as the numnber of times it's appeared
Input b:

```
grep -c "suicide" 911report/chapter-11.txt
```

Output: 

```
10
```

Comments: As we see, on one file, only the number appears

Sources used: chatGPT

chatGPT prompt:
> give me some more ways to use grep, listing only the option commands without code

chatGPT response:
> Certainly! Here are some more grep options that you can use:
> 
> -c: Count the number of matching lines instead of displaying them.
> 
> -H: Print the filename along with the matched lines when searching in multiple files.
> 
> -r: Recursively search directories and their subdirectories for matching patterns.
> 
> -x: Match the entire line, rather than just a substring. Useful for exact matches.
> 
> -s: Suppress error messages about nonexistent or unreadable files.
> 
> -E: Interpret the pattern as an extended regular expression (ERE). Allows for more advanced pattern matching.
> 
> These additional options expand the functionality of grep and provide more flexibility in your text searching and manipulation tasks.




3.  ```-B``` option

Input a:

```
grep -B 1 "terrorist" 911report/chapter-10.txt
```

Output:

```
                injured and protect against any further attacks, he said: "We will make no
                distinction between the terrorists who committed these acts and those who harbor
--
                government attorneys to seek denial of bond until such time as they were "cleared"
                of terrorist connections by the FBI and other agencies; and ordered the identity of
                the detainees kept secret. INS attorneys charged with prosecuting the immigration
                violations had trouble getting information about the detainees and any terrorist
--
                detainee list, noting that two (including Moussaoui) were linked directly to a
                terrorist organization and that it had obtained new leads helpful to the
                investigation of the 9/11 terrorist attacks.
--
                chapter 3). Ashcroft told us he was determined to take every conceivable action,
                within the limits of the Constitution, to identify potential terrorists and deter
--
                of enemy. The President tasked principals to go beyond their pre-9/11 work and
                develop a strategy to eliminate terrorists and punish those who support them. As
--
                terrorism as a threat to our way of life," an aim that would include pursuing other
                international terrorist organizations in the Middle East.
--
                to provide the United States with intelligence information;
                to continue to publicly condemn the terrorist acts;
--
                his chief lieutenants, including Ayman al Zawahiri; tell the United States what the
                Taliban knew about al Qaeda and its operations; close all terrorist camps; free all
--
                Ladin and his deputies and shut down al Qaeda camps within 24 to 48 hours, or the
                United States will use all necessary means to destroy the terrorist infrastructure.
--
                9/11 attacks, hold states and other actors responsible for providing sanctuary to
                terrorists, work with a coalition to eliminate terrorist groups and networks, and
--
                Ashcroft, Mueller, Tenet, Deputy Secretary of Defense Paul Wolfowitz, and Cofer
                Black, chief of the DCI's Counterterrorist Center.
--
                ultimatum. The President also tasked Rumsfeld to ensure that robust measures to
                protect American military forces against terrorist attack were implemented
--

            NSC staff members had begun leading meetings on terrorist fund-raising by September
--
                terrorism, not just on al Qaeda. It also incorporated the President's determination
                not to distinguish between terrorists and those who harbor them. It included a
--
                Afghanistan had already begun-included new material followed by annexes discussing
                each targeted terrorist group. The old draft directive on al Qaeda became, in
--

            The United States would strive to eliminate all terrorist networks, dry up their
--
                Hanjour's high-speed dive into the Pentagon. He told us he recalled Iraqi support
                for Palestinian suicide terrorists as well. Speculating about other possible states
--
            Secretary Powell recalled that Wolfowitz-not Rumsfeld-argued that Iraq was ultimately
                the source of the terrorist problem and should therefore be attacked.
--
                that had already been conveyed privately." The Taliban must act, and act
                immediately," he said." They will hand over the terrorists, or they will share in
--
                was not with Islam: "The enemy of America is not our many Muslim friends; it is not
                our many Arab friends. Our enemy is a radical network of terrorists, and every
--
                "Every nation, in every region, now has a decision to make: Either you are with us,
                or you are with the terrorists."
--
                begins with al Qaeda, but it does not end there," he said." It will not end until
                every terrorist group of global reach has been found, stopped, and defeated." The
```

Comments: ```-B n ``` where n is a number returns the nth line before the line where the string appears. In this example, the line before "terrorist" appears is printed out.
                
Input b:

```
grep -B 0 "terrorist" 911report/chapter-10.txt
```

Output:

```
                distinction between the terrorists who committed these acts and those who harbor
--
                of terrorist connections by the FBI and other agencies; and ordered the identity of
--
                violations had trouble getting information about the detainees and any terrorist
--
                terrorist organization and that it had obtained new leads helpful to the
                investigation of the 9/11 terrorist attacks.
--
                within the limits of the Constitution, to identify potential terrorists and deter
--
                develop a strategy to eliminate terrorists and punish those who support them. As
--
                international terrorist organizations in the Middle East.
--
                to continue to publicly condemn the terrorist acts;
--
                Taliban knew about al Qaeda and its operations; close all terrorist camps; free all
--
                United States will use all necessary means to destroy the terrorist infrastructure.
--
                terrorists, work with a coalition to eliminate terrorist groups and networks, and
--
                Black, chief of the DCI's Counterterrorist Center.
--
                protect American military forces against terrorist attack were implemented
--
            NSC staff members had begun leading meetings on terrorist fund-raising by September
--
                not to distinguish between terrorists and those who harbor them. It included a
--
                each targeted terrorist group. The old draft directive on al Qaeda became, in
--
            The United States would strive to eliminate all terrorist networks, dry up their
--
                for Palestinian suicide terrorists as well. Speculating about other possible states
--
                the source of the terrorist problem and should therefore be attacked.
--
                immediately," he said." They will hand over the terrorists, or they will share in
--
                our many Arab friends. Our enemy is a radical network of terrorists, and every
--
                or you are with the terrorists."
--
                every terrorist group of global reach has been found, stopped, and defeated." The
```

Comments: I was curious to see what would happen if I put ```-B 0```. ```grep``` will simply return the line where the detected string appears.

Sources used: chatGPT

chatGPT prompt:
> how would i find lines before and after using grep? list only the options without the codeblocks

chatGPT response:
> To find lines before and after a matching pattern using grep, you can use the following options:

-A <num>: Print <num> lines of trailing context after a match.
-B <num>: Print <num> lines of leading context before a match.
-C <num>: Print <num> lines of leading and trailing context around a match (equivalent to -A <num> and -B <num> together).
You can replace <num> with the desired number of lines you want to display before or after the match. These options allow you to include additional context around the matching lines, providing more information and context for each match.

4.  ```$``` modifier

Input a:

```
grep ";$" 911report/chapter-10.txt
```

Output:

```
                    Bin Ladin;
                    necessary military and intelligence operations;
                    other personnel to conduct operations against al Qaeda;
                to provide the United States with intelligence information;
                to continue to publicly condemn the terrorist acts;
```

Comments: ```n$``` where n is a string or character, returns all lines that end with n. In this case, I wanted to find all lines that ended with a semicolon in a file.

Input b:

```
grep "ide.$" 911report/chapter-11-txt 911report/chapter-12.txt 911report/chapter-6.txt
```

Output: 

```
911report/chapter-12.txt:                    development of an integrated system, which in turn can become part of the wider
911report/chapter-12.txt:                    terrorist attacks, the layers of security in place, and the reliability provided
911report/chapter-6.txt:                Group of principals on the investigative team's findings. The CIA's briefing slides
911report/chapter-6.txt:            The full Deputies Committee discussed al Qaeda on April 30. CIA briefing slides
```

Comments: This command also works with multiple files, where the file where the line is found is listed on the left hand side. Additionally, it works with strings as well as single characters.

Sources used: chatGPT













