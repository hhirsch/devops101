# Attack
If a server is under attack go to your log directory and enter
```
ls -latr
```

This will list the last changed files at the bottom. Particulary interesting
are large files.

Now use "tail -f" to look at the activity in the file.

You can probably watch the attacker's activity.

Then you can see how many requests the attacker made.
```
grep -ir "attacker ip" ./ | wc -l 
```

Or to get a list of the most interesting IPs you can use the following command:
```
cat /var/log/nginx/access.log | cut -d" " -f1 | sort | uniq -c | sort -rn | less
```

But it is urgent to immediately start dropping the attackers IP packets.
So maybe stop probing around and get rid of him.
