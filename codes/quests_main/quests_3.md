# 사전 준비: 실습 환경 설정
## 다음 명령어로 실습 환경을 준비하세요:
### mkdir -p ~/practice/project/{src,docs,tests,config}
### mkdir -p ~/practice/project/src/{main,utils}
### mkdir -p ~/practice/project/docs/{user,dev}
### mkdir -p ~/practice/project/tests/unit
### touch ~/practice/project/README.md
### touch ~/practice/project/src/main/app.py
### touch ~/practice/project/src/utils/helper.py
### touch ~/practice/project/docs/user/manual.txt
### touch ~/practice/project/docs/dev/api.md
### touch ~/practice/project/tests/test_main.py
### touch ~/practice/project/config/settings.conf


# 연습문제 1: 기본 상대 주소 이해.
## 1-1. 현재 위치에서 상대 주소 작성
### 현재 위치가 ~/practice/project/src/main/일 때, 다음 파일들로 이동하는 상대 주소를 작성하시오

### helper.py 파일생성


### README.md 파일

### manual.txt 파일

### settings.conf 파일


### 상대 주소 검증
### 위에서 작성한 상대 주소가 정확한지 다음 명령어로 확인하시오
### cd ~/practice/project/src/main/
```
[parkgyuseong@localhost main]$ cd ~/practice/project/src/main/
[parkgyuseong@localhost main]$ ls
app.py
[parkgyuseong@localhost main]$ 
```


# 연습문제 2: 다양한 시작점에서의 상대 주소
## 시작점 변경 실습
### 현재 위치가 ~/practice/project/docs/user/일 때

## app.py 파일로 이동하는 상대 주소를 작성
```
[parkgyuseong@localhost user]$ pwd
/home/parkgyuseong/practice/project/docs/user
[parkgyuseong@localhost user]$ cd ./../../src/main/
[parkgyuseong@localhost main]$ pwd
/home/parkgyuseong/practice/project/src/main
[parkgyuseong@localhost main]$ ls
app.py
```

## test_main.py 파일을 상대 주소를 작성하시오.
```
[parkgyuseong@localhost user]$ cd ./../../tests/
[parkgyuseong@localhost tests]$ pwd
/home/parkgyuseong/practice/project/tests
[parkgyuseong@localhost tests]$ ls
test_main.py  unit
```
## src/utils/ 디렉토리로 이동하는 상대 주소를 작성하시오.

```
[parkgyuseong@localhost user]$ cd ./../../src/utils/
[parkgyuseong@localhost utils]$ pwd
/home/parkgyuseong/practice/project/src/utils
```

# 2-2. 역방향 상대 주소
## 현재 위치가 ~/practice/project/tests/unit/일 때

### 프로젝트 루트(~/practice/project/)로 이동하는 상대 주소를 작성

```
[parkgyuseong@localhost unit]$ pwd
/home/parkgyuseong/practice/project/tests/unit
[parkgyuseong@localhost unit]$ cd ./../../
[parkgyuseong@localhost project]$ pwd
/home/parkgyuseong/practice/project
[parkgyuseong@localhost project]$ 
```

### api.md 파일로 이동하는 상대 주소를 작성
```
[parkgyuseong@localhost unit]$ pwd
/home/parkgyuseong/practice/project/tests/unit
[parkgyuseong@localhost unit]$ cd ./../../docs/dev/
[parkgyuseong@localhost dev]$ pwd
/home/parkgyuseong/practice/project/docs/dev
```

### helper.py 파일을 상대 주소를 작성하시오.

```
[parkgyuseong@localhost unit]$ pwd
/home/parkgyuseong/practice/project/tests/unit
[parkgyuseong@localhost unit]$ cd ./../../src/utils/
[parkgyuseong@localhost utils]$ pwd
/home/parkgyuseong/practice/project/src/utils
[parkgyuseong@localhost utils]$ ls
helper.py
```

# 연습문제 3: 파일 내용 확인 및 조작
## 3-1. 상대 주소를 이용한 파일 내용 출력

## 현재 위치가 ~/practice/project/src/utils/일 때

### 프로젝트 루트의 README.md 파일 내용을 출력

```
[parkgyuseong@localhost project]$ cd src/utils/
[parkgyuseong@localhost utils]$ cat ./../../README.md 
[parkgyuseong@localhost utils]$ 
```
### docs/user/manual.txt 파일 정보 자세히 출력

```
[parkgyuseong@localhost utils]$ ls -la ./../../docs/user/manual.txt 
-rw-r--r--. 1 parkgyuseong parkgyuseong 0 Jul 16 16:21 ./../../docs/user/manual.txt
```

### config/settings.conf 파일 정보 자세히 출력

```
[parkgyuseong@localhost utils]$ ls -la ./../../config/settings.conf 
-rw-r--r--. 1 parkgyuseong parkgyuseong 0 Jul 16 16:21 ./../../config/settings.conf
```
# 상대 주소를 이용한 파일 생성
## 현재 위치가 ~/practice/project/src/main/일 때

### 현재 디렉토리에 config.py 파일을 생성하고 "# Configuration module"이라는 내용을 작성

```
[parkgyuseong@localhost main]$ touch ./config.py
[parkgyuseong@localhost main]$ echo "#Configuration module" > ./config.py
[parkgyuseong@localhost main]$ ls
app.py  config.py
[parkgyuseong@localhost main]$ 
```
### tests/ 디렉토리에 test_app.py 파일을 생성하고 "# App test file"이라는 내용을 작성

```
[parkgyuseong@localhost main]$ touch ./../../tests/ test_app.py
[parkgyuseong@localhost main]$ ls ./../../tests/
test_main.py  unit 
[parkgyuseong@localhost main]$ echo "# App test file" > ./../../tests/test_app.py
```

# 연습문제 4: 파일 복사 및 이동
## 상대 주소를 이용한 파일 복사
## 현재 위치가 ~/practice/project/docs/dev/일 때
### api.md 파일을 docs/user/ 디렉토리에 api_copy.md로 복사

```
[parkgyuseong@localhost main]$ cd ~/practice/project/docs/dev/
[parkgyuseong@localhost dev]$ cp api.md ./../user/
[parkgyuseong@localhost dev]$ ls ./../user/
api.md  manual.txt
```
### src/utils/helper.py 파일을 현재 디렉토리에 복사
```
[parkgyuseong@localhost dev]$ cp ./../../src/utils/helper.py ./
[parkgyuseong@localhost dev]$ ls
api.md  helper.py
```

### config/settings.conf 파일을 tests/unit/ 디렉토리에 복사

```
[parkgyuseong@localhost dev]$ cp ./../../src/utils/helper.py ./
[parkgyuseong@localhost dev]$ ls
api.md  helper.py
[parkgyuseong@localhost dev]$ cp ./../../config/settings.conf ./../../tests/unit/
[parkgyuseong@localhost dev]$ ls ./../../tests/unit
settings.conf
```

## 상대 주소를 이용한 파일 이동
### 현재 위치가 ~/practice/project/tests/일 때
### test_main.py 파일을 tests/unit/ 디렉토리로 이동

```
[parkgyuseong@localhost dev]$ cd ~/practice/project/tests/
[parkgyuseong@localhost tests]$ mv test_main.py ./unit/
[parkgyuseong@localhost tests]$ ls ./unit/
settings.conf  test_main.py
```
### src/main/config.py 파일을 config/ 디렉토리로 이동

```
[parkgyuseong@localhost tests]$ mv ./../src/main/config.py ./../config/
[parkgyuseong@localhost tests]$ ls ./../config/
config.py  settings.conf
```
# 연습문제 5: 복합 상대 주소 활용
## 다중 파일 조작

### 현재 위치가 ~/practice/project/일 때
### src/main/ 디렉토리의 모든 파일을 docs/dev/ 디렉토리에 복사

```
[parkgyuseong@localhost project]$ cp -r ./src/main/ ./docs/dev/
[parkgyuseong@localhost project]$ ls ./docs/dev/
api.md  helper.py  main
```

### docs/user/ 디렉토리의 모든 파일을 tests/unit/ 디렉토리로 이동

```
[parkgyuseong@localhost project]$ mv ./docs/user/ ./tests/unit
[parkgyuseong@localhost project]$ ls ./tests/unit
settings.conf  test_main.py  user
```

### config/ 디렉토리 전체를 backup_config/로 복사
```
[parkgyuseong@localhost project]$ mkdir backup_config
[parkgyuseong@localhost project]$ ls
backup_config  config  docs  README.md  src  tests
[parkgyuseong@localhost project]$ cp ./config ./backup_config/
cp: -r not specified; omitting directory './config'
[parkgyuseong@localhost project]$ cp -r ./config ./backup_config/
[parkgyuseong@localhost project]$ ls 
backup_config  config  docs  README.md  src  tests
[parkgyuseong@localhost project]$ ls -la ./backup_config/
total 0
drwxr-xr-x. 3 parkgyuseong parkgyuseong 20 Jul 16 17:27 .
drwxr-xr-x. 7 parkgyuseong parkgyuseong 94 Jul 16 17:26 ..
drwxr-xr-x. 2 parkgyuseong parkgyuseong 44 Jul 16 17:27 config
```
# 연습문제 6: 에러 찾기 및 수정
## 잘못된 상대 주소 찾기
### 현재 위치가 ~/practice/project/docs/user/일 때, 다음 명령어들 중 에러가 있는 것을 찾고 올바른 명령어로 수정하시오:

### #A

### ls ../../../project/src/main/

### . 



### mv api_copy.md ../../../src/main/ 수정하기
```
[parkgyuseong@localhost user]$ mv api_copy.md ../../../src/main/
mv: cannot stat 'api_copy.md': No such file or directory
[parkgyuseong@localhost user]$ mv api.md ./../../src/main
```
## 경로 최적화
### 다음 상대 주소를 더 간단하게 경로를 최적화하시오: (cat 명령어 사용)
### 현재 위치: ~/practice/project/tests/unit/

### ../../src/main/../utils/helper.py

```
[parkgyuseong@localhost unit]$ cat ./../../src/utils/helper.py 
```
### ../../docs/user/../dev/api.md

```
[parkgyuseong@localhost unit]$ cat ./../../docs/dev/api.md
```

### ../../config/../README.md
```
[parkgyuseong@localhost unit]$ cat ./../../README.md 
```

# 연습문제 7: 종합 실습
## 7-1. 프로젝트 구조 재정리
## 현재 위치가 ~/practice/project/일 때, 다음 작업을 수행
### src/main/ 디렉토리에 models/ 하위 디렉토리를 생성

```
[parkgyuseong@localhost project]$ pwd
/home/parkgyuseong/practice/project
[parkgyuseong@localhost project]$ mkdir ./src/main/models/
[parkgyuseong@localhost project]$ ls ./src/main/models
[parkgyuseong@localhost project]$ ls ./src/main
api.md  app.py  models  test_app.py
```

### docs/ 디렉토리에 README.md 파일을 생성하고 "# Project Documentation"이라는 내용을 작성

```
[parkgyuseong@localhost project]$ cd ./docs/
[parkgyuseong@localhost docs]$ touch ./README.md
[parkgyuseong@localhost docs]$ ls 
dev  README.md  user
[parkgyuseong@localhost docs]$ echo "# Project Documentation" > ./README.md
[parkgyuseong@localhost docs]$ cat README.md 
# Project Documentation
```

### tests/unit/ 디렉토리의 모든 파일을 tests/ 디렉토리로 이동

```
[parkgyuseong@localhost project]$ mv ./tests/unit/* ./tests/
[parkgyuseong@localhost project]$ ls ./tests/
backup.txt  settings.conf  test_app.py  test_main.py  unit  user
```

### config/ 디렉토리의 모든 파일을 src/ 디렉토리에 복사
```
[parkgyuseong@localhost project]$ cp -r ./config/ ./src/
[parkgyuseong@localhost project]$ ls ./src/
config  main  utils
```
## 7-2. 백업 및 정리
### 현재 위치가 ~/practice/project/src/main/일 때
### 현재 내용을 ../../project_backup/으로 복사

```
[parkgyuseong@localhost main]$ mkdir ./../../project_backup
[parkgyuseong@localhost main]$ ls ./../../
backup_config  config  docs  project_backup  README.md  src  tests
[parkgyuseong@localhost main]$ cp * ./../../project_backup/
cp: -r not specified; omitting directory 'models'
[parkgyuseong@localhost main]$ cp -r * ./../../project_backup/
[parkgyuseong@localhost main]$ ls ./../../project_backup/
api.md  app.py  models  test_app.py
[parkgyuseong@localhost main]$ 
```
### utils/ 디렉토리의 모든 .py 파일을 현재 디렉토리의 models/ 디렉토리로 복사

```
[parkgyuseong@localhost main]$ cp ./../utils/* ./
[parkgyuseong@localhost main]$ ls
api.md  app.py  helper.py  models  test_app.py
```

### 프로젝트 루트의 README.md 파일을 현재 디렉토리에 PROJECT_INFO.md로 복사

```
[parkgyuseong@localhost main]$ cp ./../../README.md ./PROJECT_INFO.md
[parkgyuseong@localhost main]$ ls ./
api.md  app.py  helper.py  models  PROJECT_INFO.md  test_app.py
```
















