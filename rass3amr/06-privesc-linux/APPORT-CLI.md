
## generate a crash (core dumped)
```c
int main() { 
	int *ptr = NULL; 
	*ptr = 42; 
}
```

- **python one liner**

```bash
python3 -c 'import ctypes;ctypes.string_at(0)'
```

```bash
sudo /usr/bin/apport-cli -c /var/crash/XXXXXX.crash
# press V (view report)
!/bin/bash
```

