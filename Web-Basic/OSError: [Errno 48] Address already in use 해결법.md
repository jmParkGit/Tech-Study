# OSError: [Errno 48] Address already in use 해결법

1. lsof shell cmd로 PID확인
```shell
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding  lsof -i TCP:5001
COMMAND  PID       USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
Python  5860 parkjaemin    6u  IPv4 0x2d41538d45548b2d      0t0  TCP *:commplex-link (LISTEN)
Python  5861 parkjaemin    6u  IPv4 0x2d41538d45548b2d      0t0  TCP *:commplex-link (LISTEN)
Python  5861 parkjaemin    7u  IPv4 0x2d41538d45548b2d      0t0  TCP *:commplex-link (LISTEN)
```

2. kill
```shell
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding  kill -9 5860
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding  kill -9 5861
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding  lsof -i TCP:5001
 ✘ parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding 
 
```
