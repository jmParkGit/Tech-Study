# netstat -tulpn
```Shell
root@ip-172-31-11-163:/home/ubuntu# netstat -tulpn
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      10980/docker-proxy
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      14370/systemd-resol
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      12835/sshd
tcp        0      0 0.0.0.0:27017           0.0.0.0:*               LISTEN      11001/docker-proxy
tcp6       0      0 :::80                   :::*                    LISTEN      10987/docker-proxy
tcp6       0      0 :::22                   :::*                    LISTEN      12835/sshd
tcp6       0      0 :::27017                :::*                    LISTEN      11006/docker-proxy
udp        0      0 127.0.0.53:53           0.0.0.0:*                           14370/systemd-resol
udp        0      0 172.31.11.163:68        0.0.0.0:*                           14356/systemd-netwo
```
