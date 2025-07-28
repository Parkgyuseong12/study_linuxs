## **✅ 문제 : 간단한 서버 관리 스크립트 작성**

### **🔧 요구사항**

* `start`: 포트 8000에서 `http.server`를 백그라운드로 실행 (`nohup`, 로그는 `server.log`)

* `stop`: 실행 중인 프로세스를 찾아 종료

* `status`: 프로세스가 실행 중인지 확인하여 출력

* `restart`: 중지 후 다시 실행

  ### **🎯 실행 예시**

  $ ./webserver.sh start  
  서버가 백그라운드에서 시작되었습니다.  
    
  $ ./webserver.sh status  
  서버 실행 중입니다. PID: 13579  
    
  $ ./webserver.sh stop  
  서버가 종료되었습니다.  
    
  $ ./[webserver.sh](http://webserver.sh) tail\_log  
  … log message 확인


문제 모두 조건에 따라:

* `if [ "$1" == "start" ]` 식으로 흐름 제어

* 변수 `PORT`, `PID`, `LOGFILE` 등을 정의해 구성 가능


```
#!/bin/bash

PORT="8000"
PID="$(ps aux | grep "http" | grep "server" | tr -s ' ' | cut -d " " -f2)"
LOGFILE="server.log"


if [ "$1" == "start" ]; then
        nohup python3 -m http.server"$PORT" --bind 0.0.0.0 &>> "$LOGFILE" &
        echo " 서버가 백그라운드에서 시작되었습니다. "
elif [ "$1" == "stop" ]; then
        kill "$PID"
        echo " 서버가 종료되었습니다. "

elif [ "$1" == "status" ]; then
        if [ -z "$PID" ]; then
                echo " 서버가 실행 중이지 않습니다."
        else
                echo " 서버가 실행 중 입니다. PID = "$PID" "
        fi

elif [ "$1" == "tail_log" ]; then
        cat "$LOGFILE"
else

        echo "end"
fi


[parkgyuseong@192.168.0.42 ~/Downloads]$ source ./webserver.sh start
 서버가 백그라운드에서 시작되었습니다. 

[parkgyuseong@192.168.0.42 ~/Downloads]$ source ./webserver.sh stop
bash: kill: `': not a pid or valid job spec
 서버가 종료되었습니다. 
[1]+  Exit 1                  nohup python3 -m http.server"$PORT" --bind 0.0.0.0 &>> "$LOGFILE"

[parkgyuseong@192.168.0.42 ~/Downloads]$ source ./webserver.sh status
 서버가 실행 중이지 않습니다.



```