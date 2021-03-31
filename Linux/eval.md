```
/home/user1 > a="ls | more"
/home/user1 > $a
bash: command not found: ls | more
/home/user1 > # Above command didn't work as ls tried to list file with name pipe (|) and more. But these files are not there
/home/user1 > eval $a
file.txt
mailids
remote_cmd.sh
sample.txt
tmp
/home/user1 >
```
