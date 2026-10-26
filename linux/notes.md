# Linux troubleshooting notes
lakshmi practice
## Disk full
- df -h              check which filesystem is full
- df -ih             check if inodes are full
- du -h --max-depth=1 /path    find which folder is big
- find /path -type f -size +500M    find large files
- truncate -s 0 file.log    empty a log file safely

## Port conflict
- sudo lsof -i :PORT -sTCP:LISTEN    find who owns the port
- kill PID           stop it gracefully
- kill -9 PID        force stop
