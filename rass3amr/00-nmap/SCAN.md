# WHAT is NMAP ? 

```bash
nmap $IP -Pn -oA TCPbasicScan
```

```bash
sudo nmap -p- -sV -sC -O -Pn --disable-arp-ping $IP -oA FullTCP
```