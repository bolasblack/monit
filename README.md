# monit

## How to know webhook data struct

Run command:

```bash
while true; do nc -vlp 12345; echo "\n"; done
```

Add config to `/etc/monitrc`:

```
set mmonit http://127.0.0.1:12345/collector
```

[data struct explanations](data_struct.md)
