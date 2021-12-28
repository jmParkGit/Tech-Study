# service docker status
```Shell
ubuntu@ip-172-31-11-163:~$ service docker status
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Tue 2021-12-28 01:25:36 KST; 19h ago
     Docs: https://docs.docker.com
 Main PID: 32673 (dockerd)
    Tasks: 7
   CGroup: /system.slice/docker.service
           └─32673 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

Dec 28 01:25:35 ip-172-31-11-163 dockerd[32673]: time="2021-12-28T01:25:35.667399812+09:00" level=warning msg="Your kernel does not support CPU realtime scheduler"
Dec 28 01:25:35 ip-172-31-11-163 dockerd[32673]: time="2021-12-28T01:25:35.667549503+09:00" level=warning msg="Your kernel does not support cgroup blkio weight"
Dec 28 01:25:35 ip-172-31-11-163 dockerd[32673]: time="2021-12-28T01:25:35.667689172+09:00" level=warning msg="Your kernel does not support cgroup blkio weight_device"
Dec 28 01:25:35 ip-172-31-11-163 dockerd[32673]: time="2021-12-28T01:25:35.668026748+09:00" level=info msg="Loading containers: start."
Dec 28 01:25:35 ip-172-31-11-163 dockerd[32673]: time="2021-12-28T01:25:35.792207702+09:00" level=info msg="Default bridge (docker0) is assigned with an IP address 172.17.0.0/16
Dec 28 01:25:35 ip-172-31-11-163 dockerd[32673]: time="2021-12-28T01:25:35.905012193+09:00" level=info msg="Loading containers: done."
Dec 28 01:25:35 ip-172-31-11-163 dockerd[32673]: time="2021-12-28T01:25:35.997056163+09:00" level=info msg="Docker daemon" commit=459d0df graphdriver(s)=overlay2 version=20.10.1
Dec 28 01:25:35 ip-172-31-11-163 dockerd[32673]: time="2021-12-28T01:25:35.997469994+09:00" level=info msg="Daemon has completed initialization"
Dec 28 01:25:36 ip-172-31-11-163 systemd[1]: Started Docker Application Container Engine.
Dec 28 01:25:36 ip-172-31-11-163 dockerd[32673]: time="2021-12-28T01:25:36.039831322+09:00" level=info msg="API listen on /var/run/docker.sock"
```
