# pm2 명령여
## pm2 설치
```shell
sudo npm install -g pm2
```

## pm2로 app실행
```shell
$ pm2 start app.js
[PM2] Applying action restartProcessId on app [app](ids: [ 0 ])
[PM2] [app](0) ✓
[PM2] Process successfully started
┌─────┬────────┬─────────────┬─────────┬─────────┬──────────┬────────┬──────┬───────────┬──────────┬──────────┬──────────┬──────────┐
│ id  │ name   │ namespace   │ version │ mode    │ pid      │ uptime │ ↺    │ status    │ cpu      │ mem      │ user     │ watching │
├─────┼────────┼─────────────┼─────────┼─────────┼──────────┼────────┼──────┼───────────┼──────────┼──────────┼──────────┼──────────┤
│ 0   │ app    │ default     │ 1.0.0   │ fork    │ 30782    │ 0s     │ 2    │ online    │ 0%       │ 14.1mb   │ ubuntu   │ disabled │
└─────┴────────┴─────────────┴─────────┴─────────┴──────────┴────────┴──────┴───────────┴──────────┴──────────┴──────────┴──────────┘
```

## pm2로 로그 확인
```shell
$ pm2 logs
[TAILING] Tailing last 15 lines for [all] processes (change the value with --lines option)
/home/ubuntu/.pm2/pm2.log last 15 lines:
PM2        | 2022-05-30T00:04:36: PM2 log: App [app:0] starting in -fork mode-
PM2        | 2022-05-30T00:04:36: PM2 log: App [app:0] online
...
...
```

## pm2 app 상태 리스트
```shell
$ pm2 list
┌─────┬────────┬─────────────┬─────────┬─────────┬──────────┬────────┬──────┬───────────┬──────────┬──────────┬──────────┬──────────┐
│ id  │ name   │ namespace   │ version │ mode    │ pid      │ uptime │ ↺    │ status    │ cpu      │ mem      │ user     │ watching │
├─────┼────────┼─────────────┼─────────┼─────────┼──────────┼────────┼──────┼───────────┼──────────┼──────────┼──────────┼──────────┤
│ 0   │ app    │ default     │ 1.0.0   │ fork    │ 30782    │ 3m     │ 2    │ online    │ 0%       │ 64.5mb   │ ubuntu   │ disabled │
└─────┴────────┴─────────────┴─────────┴─────────┴──────────┴────────┴──────┴───────────┴──────────┴──────────┴──────────┴──────────┘
```


## pm2 app 중지
- ```pm2 stop {id}
```shell
$ pm2 stop 0
[PM2] Applying action stopProcessId on app [0](ids: [ '0' ])
[PM2] [app](0) ✓
┌─────┬────────┬─────────────┬─────────┬─────────┬──────────┬────────┬──────┬───────────┬──────────┬──────────┬──────────┬──────────┐
│ id  │ name   │ namespace   │ version │ mode    │ pid      │ uptime │ ↺    │ status    │ cpu      │ mem      │ user     │ watching │
├─────┼────────┼─────────────┼─────────┼─────────┼──────────┼────────┼──────┼───────────┼──────────┼──────────┼──────────┼──────────┤
│ 0   │ app    │ default     │ 1.0.0   │ fork    │ 0        │ 0      │ 2    │ stopped   │ 0%       │ 0b       │ ubuntu   │ disabled │
└─────┴────────┴─────────────┴─────────┴─────────┴──────────┴────────┴──────┴───────────┴──────────┴──────────┴──────────┴──────────┘
```
