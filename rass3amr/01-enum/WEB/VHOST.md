
```bash
ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/bitquark-subdomainstop100000.txt:FUZZ -u URL -H 'Host: FUZZ.$domain' -fw 4 - t 100
```
