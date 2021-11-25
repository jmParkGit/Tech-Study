# mac - 특정 포트를 사용중인 프로세스 확인/종료
```shell
✘ ⚙ parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/JM_productReviewApp   main ±  sudo lsof -i :19000
COMMAND   PID       USER   FD   TYPE            DEVICE SIZE/OFF NODE NAME
node    34163 parkjaemin   33u  IPv6 0xe44b089a8a16cd3      0t0  TCP *:igrid (LISTEN)
node    34163 parkjaemin   35u  IPv6 0xe44b089a8a14393      0t0  TCP 192.168.0.22:igrid->192.168.0.11:41304 (ESTABLISHED)
 ⚙ parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/JM_productReviewApp   main ±  kill -9 34163
 ⚙ parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/JM_productReviewApp   main ±  sudo lsof -i :19000
 ✘ ⚙ parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/JM_productReviewApp   main ± 
```
