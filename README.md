# Linux-commands

1. Display name of current logged-in user -- whoami
2. Check system date or time -- date or
3. Display only date -- date %D
4. Display only time(hour,min,sec) -- date %T
5. Display only hour and minute -- date %H:%M
6. Display files and folders in the human readable format -- ls -lh
7. Clean the screen -- ctrl+l or clear
8. Read a file and search
less <file>
For top to bottom: use /<search_keyword> and click 'n' for next
For bottom to top search: use ?<search_keyword> and click 'n' for next
use 'shift + g' for moving to last line directly and go back to the first line just click 'p'
10. View content of a file page by page -- more <file>
 use down arrow for next page
11. Absolute path -- /home/pra-y/myfolder/newfolder
12. Relative Path -- myfolder/newfolder
13. Read or display top 5 lines of file --> head -5 <file>
14. Read or display bottom 5 lines of file --> tail -5 <file>
15. Sort a file --> sort <file> or sort -r <file>
16. Display unique content of file --> sort <file> | uniq
17. A file has 9 lines and how to split this file in 3 different files --> split -l 3 <file>
18. Search a word or string and display matching content from file --> grep "word" <file>
19. Search multiple words and display matching content from file --> egrep "word1|WORD2" <file>
20. How to use WILDCARDS in linux *,[],{} -->
ls file\*  For e.g. - ls *.csv
touch file {1..5}  For e.g.- touch file{1..5}
22. Shuffle content of file --> shuf <file>
23. Count no. of line in a file --> wc -l <file>
24. Check if two files are identical --> cmp fileA fileB
25. Compare and display difference b/w two files --> diff -u fileA fileB
26. Find a file
Method1: find /path/ -name <file>
Method2: First install locate
'sudo updatedb' then Run 'locate <file>'
27. Read or get more info about command --> man ls or ls --help | more
28. Check which executable is using for a command --> which ls
29. Use calculator in linux --> bc
30. Check calendar of month or year --> cal or cal JAN 2023 or cal 2024
31. Check how long server has been running --> uptime
32. Record your activity on terminal in a file --> script & ctrl + d for exit
