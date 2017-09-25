# Utility

## `awk`

프로세스 `ps` list 정리.

```bash
$ cat ps.txt |awk '{print $1, $9}' | sort +1 | sort | uniq > ps_summary.txt
```