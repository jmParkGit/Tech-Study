# mongodb 명령어
- mongo db 실행
```Shell
service mongod start
```

- mongo db 재실행
```Shell
service mongod restart
```

- mongodb 중지
```Shell
service mongod stop
```

-mongodb 상태확인
```Shell
service mongod status
```
```Shell
root@ip-172-31-11-163:/home/ubuntu# service mongod status
● mongod.service - MongoDB Database Server
   Loaded: loaded (/lib/systemd/system/mongod.service; disabled; vendor preset: enabled)
   Active: active (running) since Tue 2021-12-28 23:27:09 KST; 3s ago
     Docs: https://docs.mongodb.org/manual
 Main PID: 12312 (mongod)
   CGroup: /system.slice/mongod.service
           └─12312 /usr/bin/mongod --config /etc/mongod.conf

```
