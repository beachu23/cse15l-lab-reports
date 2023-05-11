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

The command allows ```grep``` to search for multiple string patterns in the file. If either pattern shows up in the file, the line will be included in the output. 

Input b:

```
grep -e "suicide"  911report/chapter-1.txt
```

Output: 

```
the hijacking would take the traditional form: that is, it would not be a suicide hijacking designed to convert the aircraft into a guided missile.
```

If only one string is passed to ```grep```, it will function as if the ```-e``` option does not exist. In other words, it will simply search for the one string presented.

2. ```






