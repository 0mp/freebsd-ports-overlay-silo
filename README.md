# FreeBSD Ports Overlay for Silo

## Usage

```sh
poudriere ports -c -p overlay_silo -U https://github.com/0mp/freebsd-ports-overlay-silo
poudriere bulk -p "$ports" -O overlay_silo -j "$jail" -- www/silo-pgsty www/mcli-pgsty www/silo-console-pgsty
```
