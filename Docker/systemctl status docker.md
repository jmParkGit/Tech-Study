# systemctl status docker
- systemctl {명령} {서비스명}
- status는 서비스상태 확인
```Shell
ubuntu@ip-172-31-11-163:~$ sudo systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Tue 2021-12-28 01:25:36 KST; 29s ago
     Docs: https://docs.docker.com
 Main PID: 32673 (dockerd)
    Tasks: 7
   CGroup: /system.slice/docker.service
           └─32673 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
```
