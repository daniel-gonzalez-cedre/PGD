The program now reads steamed data from standard input and writes to standard output.

In order to know when to stop reading, the program assumes it will eventually read a line with the character "X" and halts reading after that character is read.

The easiest way to get around this without modifying the data itself is to create a file (named e.g., EOF.txt) containing only the character "X" and use cat to pipe it in after the data, as below:

```bash
cat .data/karate.g ./data/EOF.txt | ./pgd -f ./dummy.txt -c dummy.txt
```

The flag `c` is necessary in order to receive any output at all. It takes a filename, and creates a blank file with that filename. I suggest using a filename for a file that does not exist, so that no data is accidentally overwritten.
