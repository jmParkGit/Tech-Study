
# 에러로그
```Shell
ubuntu@ip-172-31-11-163:~$ sudo apt-get install openjdk-8-jdk
...
...
dpkg-deb (subprocess): failed to create directory: No space left on device
dpkg-deb: error: tar subprocess returned error exit status 2
dpkg: error processing archive /tmp/apt-dpkg-install-Bt9dsQ/124-openjdk-8-jdk_8u312-b07-0ubuntu1~18.04_amd64.deb (--unpack):
 dpkg-deb --control subprocess returned error exit status 2
dpkg: error: failed to write status database record about 'libedit2:amd64' to '/var/lib/dpkg/status': No space left on deviceNo apport report written because MaxReports is reached already

E: Sub-process /usr/bin/dpkg returned an error code (2)
```

# 원인
- 리눅스 partition이 꽉차면 일어나는 에러
```Shell
ubuntu@ip-172-31-11-163:~$ df -h
Filesystem      Size  Used Avail Use% Mounted on
udev            476M     0  476M   0% /dev
tmpfs            98M  796K   98M   1% /run
/dev/xvda1      7.7G  7.6G   81M  99% /
tmpfs           490M     0  490M   0% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
tmpfs           490M     0  490M   0% /sys/fs/cgroup
/dev/loop2       34M   34M     0 100% /snap/amazon-ssm-agent/3552
/dev/loop5       25M   25M     0 100% /snap/amazon-ssm-agent/4046
/dev/loop0       56M   56M     0 100% /snap/core18/2253
/dev/loop6       44M   44M     0 100% /snap/snapd/14295
/dev/loop4       56M   56M     0 100% /snap/core18/2284
/dev/loop3       44M   44M     0 100% /snap/snapd/14549
tmpfs            98M     0   98M   0% /run/user/1000
```

# 해결책
- partition정리
```Shell
ubuntu@ip-172-31-11-163:~$ df -h
Filesystem      Size  Used Avail Use% Mounted on
udev            476M     0  476M   0% /dev
tmpfs            98M  796K   98M   1% /run
/dev/xvda1      7.7G  4.4G  3.4G  57% /
tmpfs           490M     0  490M   0% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
tmpfs           490M     0  490M   0% /sys/fs/cgroup
/dev/loop2       34M   34M     0 100% /snap/amazon-ssm-agent/3552
/dev/loop5       25M   25M     0 100% /snap/amazon-ssm-agent/4046
/dev/loop0       56M   56M     0 100% /snap/core18/2253
/dev/loop6       44M   44M     0 100% /snap/snapd/14295
/dev/loop4       56M   56M     0 100% /snap/core18/2284
/dev/loop3       44M   44M     0 100% /snap/snapd/14549
tmpfs            98M     0   98M   0% /run/user/1000
```
