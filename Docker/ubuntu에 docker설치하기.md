# ubuntu에 docker설치하기
## 환경
```Shell
root@ip-172-31-11-163:/home/ubuntu# cat /etc/issue
Ubuntu 18.04.5 LTS \n \l
```

## 설치 shell 명령어
```Shell
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
sudo apt update
apt-cache policy docker-ce
sudo apt install docker-ce
```

## 설치후 docker 실행되는지 확인하기
```Shell
sudo systemctl status docker
```
```Shell
root@ip-172-31-11-163:/home/ubuntu# sudo systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Tue 2021-12-28 01:25:36 KST; 21h ago
     Docs: https://docs.docker.com
 Main PID: 32673 (dockerd)
    Tasks: 12
   CGroup: /system.slice/docker.service
           └─32673 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
```
