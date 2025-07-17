# Linux 파일 관리 명령어 와일드카드 실습 문제

## 실습 환경 설정

**먼저 다음 명령어들을 실행하여 실습 환경을 구성하세요:**

\# 실습 디렉터리 생성

mkdir wildcard\_file\_practice

cd wildcard\_file\_practice

\# 테스트 파일들 생성

touch report1.txt report2.txt report3.txt

touch data1.csv data2.csv data3.csv data\_old.csv

touch image1.jpg image2.jpg image3.png photo.gif

touch backup\_2023.tar backup\_2024.tar config.conf

touch log\_error.txt log\_access.txt log\_system.txt

touch temp1.tmp temp2.tmp temp3.tmp

touch file\_001.dat file\_002.dat file\_010.dat

touch script1.sh script2.sh test\_script.sh

touch document.pdf presentation.ppt spreadsheet.xls

touch readme.md changelog.md license.txt

touch old\_report.txt new\_report.txt final\_report.txt

\# 기본 디렉터리들 생성

mkdir archives backup logs images documents scripts
```
[parkgyuseong@localhost Downloads]$ mkdir  wildcard\_file\_practice && cd wildcard\_file\_practice && touch report{1,2,3}.txt data{1,2,3}.csv data\_old.csv image{1,2}.jpg image3.png photo.gif backup\_{2023,2024}.tar config.conf log\{error,access}.txt log\_system.txt temp{1,2,3}.tmp file\_{001,002,010}.dat script{1,2}.sh test\_script.sh document.pdf presentation.ppt spreadsheet.xls readme.md chagelog.md license.txt {old\,new\, final\}_report.txt && mkdir archives backup logs images documents scripts && ls
archives         document.pdf       license.txt            report3.txt
backup           documents          log{error,access}.txt  script1.sh
backup_2023.tar  file_001.dat       logs                   script2.sh
backup_2024.tar  file_002.dat       log_system.txt         scripts
chagelog.md      file_010.dat       {old,new,              spreadsheet.xls
config.conf      final}_report.txt  photo.gif              temp1.tmp
data1.csv        image1.jpg         presentation.ppt       temp2.tmp
data2.csv        image2.jpg         readme.md              temp3.tmp
data3.csv        image3.png         report1.txt            test_script.sh
data_old.csv     images             report2.txt

```

---

## 1\. mkdir 명령어 와일드카드 실습

### 1-1. 연도별 백업 디렉터리 생성

\# 2020년부터 2024년까지 백업 디렉터리를 한 번에 생성하세요

\# 예: backup\_2020, backup\_2021, backup\_2022, backup\_2023, backup\_2024



\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ mkdir backup{2020,2021,2022,2023,2024} && ls
archives         chagelog.md   file_002.dat           logs              script1.sh
backup           config.conf   file_010.dat           log_system.txt    script2.sh
backup2020       data1.csv     final}_report.txt      {old,new,         scripts
backup2021       data2.csv     image1.jpg             photo.gif         spreadsheet.xls
backup2022       data3.csv     image2.jpg             presentation.ppt  temp1.tmp
backup2023       data_old.csv  image3.png             readme.md         temp2.tmp
backup_2023.tar  document.pdf  images                 report1.txt       temp3.tmp
backup2024       documents     license.txt            report2.txt       test_script.sh
backup_2024.tar  file_001.dat  log{error,access}.txt  report3.txt

```


### 1-2. 월별 로그 디렉터리 생성

\# logs 디렉터리 안에 01월부터 12월까지 디렉터리 생성

\# 예: logs/log\_01, logs/log\_02, ..., logs/log\_12

\# 명령어를 작성하세요:
```
[parkgyuseong@localhost wildcard_file_practice]$ cd logs && mkdir log{01,02,03,04,05,06,07,08,09,10,11,12} && ls
log01  log02  log03  log04  log05  log06  log07  log08  log09  log10  log11  log12

```

### 1-3. 프로젝트별 디렉터리 생성

\# project\_A, project\_B, project\_C 디렉터리를 한 번에 생성하세요

\# 명령어를 작성하세요:
```
[parkgyuseong@localhost wildcard_file_practice]$ mkdir project{A,B,C} && ls
archives         config.conf   final}_report.txt      photo.gif         script2.sh
backup           data1.csv     image1.jpg             presentation.ppt  scripts
backup2020       data2.csv     image2.jpg             projectA          spreadsheet.xls
backup2021       data3.csv     image3.png             projectB          temp1.tmp
backup2022       data_old.csv  images                 projectC          temp2.tmp
backup2023       document.pdf  license.txt            readme.md         temp3.tmp
backup_2023.tar  documents     log{error,access}.txt  report1.txt       test_script.sh
backup2024       file_001.dat  logs                   report2.txt
backup_2024.tar  file_002.dat  log_system.txt         report3.txt
chagelog.md      file_010.dat  {old,new,              script1.sh

```

### 1-4. 계층적 디렉터리 생성

\# data/2024/{01,02,03} 구조로 디렉터리를 생성하세요

\# (data 디렉터리 안에 2024 디렉터리, 그 안에 01, 02, 03 디렉터리)

\# 명령어를 작성하세요:
```
[parkgyuseong@localhost wildcard_file_practice]$ mkdir -p data/2024/{01,02,03} && cd data/2024/ && ls
01  02  03

```
---

## 2\. cp 명령어 와일드카드 실습

### 2-1. 확장자별 파일 복사

\# 모든 .txt 파일을 backup 디렉터리로 복사하세요

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost data]$ cd ..
[parkgyuseong@localhost wildcard_file_practice]$ cp *.txt backup/ && cd backup/ && ls
final}_report.txt  log{error,access}.txt  report1.txt  report3.txt
license.txt        log_system.txt         report2.txt

```

### 2-2. 특정 패턴 파일 복사

\# "report"로 시작하는 모든 파일을 documents 디렉터리로 복사하세요

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ cp report*.* documents/ && cd documents/ && ls
report1.txt  report2.txt  report3.txt

```

### 2-3. 숫자가 포함된 파일 복사

\# 파일명에 숫자가 포함된 모든 이미지 파일(.jpg, .png)을 images 디렉터리로 복사하세요

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ mv image*.* images/ && cd images/ && ls
image1.jpg  image2.jpg  image3.png
[parkgyuseong@localhost images]$ pwd
/home/parkgyuseong/Downloads/wildcard_file_practice/images

```

### 2-4. 특정 범위의 파일 복사

\# data1.csv, data2.csv, data3.csv 파일만 backup 디렉터리로 복사하세요

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ cp data{1,2,3}.csv backup
backup/          backup2021/      backup2023/      backup2024/      
backup2020/      backup2022/      backup_2023.tar  backup_2024.tar  
[parkgyuseong@localhost wildcard_file_practice]$ cp data{1,2,3}.csv backup/ && cd backup/ && ls
data1.csv  data3.csv          license.txt            log_system.txt  report2.txt
data2.csv  final}_report.txt  log{error,access}.txt  report1.txt     report3.txt

```

### 2-5. 복합 조건 파일 복사

\# "log\_"로 시작하는 .txt 파일들을 logs 디렉터리로 복사하세요

\# 명령어를 작성하세요:
```
[parkgyuseong@localhost wildcard_file_practice]$ cp log_{access,error}.txt logs/
[parkgyuseong@localhost wildcard_file_practice]$ cd logs/ && ls
log01  log03  log05  log07  log09  log11  log_access.txt
log02  log04  log06  log08  log10  log12  log_error.txt

```

---

## 3\. mv 명령어 와일드카드 실습

### 3-1. 임시 파일 이동

\# 모든 .tmp 파일을 temp 디렉터리로 이동하세요 (mkdir temp 먼저 실행)

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ mkdir temp && mv *.tmp temp/ && cd temp && ls
temp1.tmp  temp2.tmp  temp3.tmp

```

### 3-2. 백업 파일 정리

\# "backup\_"로 시작하는 모든 파일을 archives 디렉터리로 이동하세요

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ mv backup_*.tar archives/ && cd archives/ && ls
backup_2023.tar  backup_2024.tar
```

### 3-3. 스크립트 파일 정리

\# 모든 .sh 파일을 scripts 디렉터리로 이동하세요

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ mv *.sh scripts/ && cd scripts/ && ls
script1.sh  script2.sh  test_script.sh

```

### 3-4. 특정 패턴 파일 이동

\# "file\_"로 시작하고 3자리 숫자가 포함된 .dat 파일들을 data 디렉터리로 이동하세요

\# (data 디렉터리가 없다면 먼저 생성)

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ mv file_{001,002,010}.dat data/ && cd data/ && ls
2024  file_001.dat  file_002.dat  file_010.dat

```

### 3-5. 조건부 파일 이동

\# "old\_" 또는 "new\_"로 시작하는 모든 파일을 archives 디렉터리로 이동하세요

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ mv {old,new}_report.txt archives/ && cd archives/ && ls
backup_2023.tar  backup_2024.tar  new_report.txt  old_report.txt

```

---

## 4\. rm 명령어 와일드카드 실습

### 4-1. 임시 파일 삭제

\# 모든 .tmp 파일을 삭제하세요 (주의: 실제로는 신중히 실행)

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ cd temp/ && rm temp*.tmp && ls
[parkgyuseong@localhost temp]$ 

```

### 4-2. 특정 패턴 파일 삭제

\# "temp"로 시작하는 모든 파일을 삭제하세요

\# 명령어를 작성하세요:

```

```

### 4-3. 백업 파일 정리

\# 2023년 백업 파일만 삭제하세요 (backup\_2023.tar)

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ cd archives/ && rm backup_2023.tar && ls
backup_2024.tar  new_report.txt  old_report.txt

```

### 4-4. 조건부 파일 삭제

\# 확장자가 3글자가 아닌 파일들을 삭제하세요

\# 힌트: 확장자가 .jpg, .png, .gif, .txt, .csv, .tar, .dat, .pdf, .ppt, .xls가 아닌 파일

\# 명령어를 작성하세요:

```
[parkgyuseong@localhost wildcard_file_practice]$ rm *.md && ls
archives    config.conf   documents          logs              report1.txt
backup      data          final_report.txt   log_system.txt    report2.txt
backup2020  data1.csv     final}_report.txt  photo.gif         report3.txt
backup2021  data2.csv     images             presentation.ppt  scripts
backup2022  data3.csv     license.txt        projectA          spreadsheet.xls
backup2023  data_old.csv  log_access.txt     projectB          temp
backup2024  document.pdf  log_error.txt      projectC


```

---

## 5\. 복합 명령어 실습

### 5-1. 파일 정리 시스템

\# 1단계: 모든 이미지 파일(.jpg, .png, .gif)을 images 디렉터리로 이동

\# 2단계: 모든 문서 파일(.pdf, .ppt, .xls, .md)을 documents 디렉터리로 이동

\# 3단계: 모든 데이터 파일(.csv, .dat)을 data 디렉터리로 이동 (없으면 생성)

\# 명령어들을 작성하세요:
```
[parkgyuseong@localhost wildcard_file_practice]$ mv photo.gif images/ && mv *.{pdf,ppt,xls,md} documents/ && mv *.{csv,dat} data/

```

### 5-2. 백업 및 정리 작업

\# 1단계: 모든 .txt 파일을 backup/txt\_files 디렉터리로 복사 (디렉터리 생성 필요)

\# 2단계: 모든 설정 파일(.conf)을 backup/config 디렉터리로 복사

\# 3단계: 원본 설정 파일들을 삭제

\# 명령어들을 작성하세요:
```

[parkgyuseong@localhost wildcard_file_practice]$ mkdir files/ && cp *.txt ./files/ && mkdir backup/config/ && cp *.conf backup/config/
[parkgyuseong@localhost wildcard_file_practice]$ rm *.conf
[parkgyuseong@localhost wildcard_file_practice]$ ls
archives    backup2023  data3.csv         final}_report.txt  logs            report1.txt
backup      backup2024  data_old.csv      images             log_system.txt  report2.txt
backup2020  data        documents         license.txt        projectA        report3.txt
backup2021  data1.csv   files             log_access.txt     projectB        scripts
backup2022  data2.csv   final_report.txt  log_error.txt      projectC        temp

```

### 5-3. 날짜별 로그 정리

\# 1단계: logs 디렉터리에 error, access, system 하위 디렉터리 생성

\# 2단계: log\_error.txt를 logs/error/로 이동

\# 3단계: log\_access.txt를 logs/access/로 이동

\# 4단계: log\_system.txt를 logs/system/로 이동

\# 명령어들을 작성하세요:

---

## 6\. 고급 와일드카드 실습

### 6-1. 복잡한 패턴 매칭

\# "report" 또는 "data"로 시작하고 숫자가 포함된 모든 파일을 찾아서 processed 디렉터리로 복사하세요

\# 명령어를 작성하세요:

### 6-2. 제외 패턴 활용

\# 모든 파일 중에서 "final\_"로 시작하지 않는 .txt 파일들을 draft 디렉터리로 이동하세요

\# 명령어를 작성하세요:

### 6-3. 범위 지정 패턴

\# 파일명에 001부터 009까지의 숫자가 포함된 파일들을 single\_digit 디렉터리로 복사하세요

\# 명령어를 작성하세요:

---

## 7\. 실전 시나리오 문제

### 7-1. 프로젝트 정리 시나리오

\# 시나리오: 프로젝트 종료 후 파일 정리

\# 1\. 완료된 리포트 파일들(report\*.txt)을 completed 디렉터리로 이동

\# 2\. 작업 중인 파일들(temp\*, \*\_draft)을 ongoing 디렉터리로 이동

\# 3\. 백업 파일들(backup\_\*)을 archive 디렉터리로 이동

\# 4\. 불필요한 임시 파일들(\*.tmp)을 삭제

\# 명령어들을 작성하세요:

### 7-2. 로그 관리 시나리오

\# 시나리오: 서버 로그 정리

\# 1\. 2024년 로그 파일들을 logs/2024 디렉터리로 이동

\# 2\. 에러 로그들을 logs/errors 디렉터리로 복사

\# 3\. 2023년 로그 파일들을 삭제

\# 4\. 시스템 로그들을 logs/system 디렉터리로 이동

\# 명령어들을 작성하세요:

### 7-3. 개발 환경 정리 시나리오

\# 시나리오: 개발 프로젝트 구조 정리

\# 1\. 모든 스크립트 파일(\*.sh)을 scripts 디렉터리로 이동

\# 2\. 설정 파일들(\*.conf, \*.config)을 config 디렉터리로 복사

\# 3\. 문서 파일들(\*.md, \*.txt)을 docs 디렉터리로 이동

\# 4\. 데이터 파일들(\*.csv, \*.dat)을 data 디렉터리로 이동

\# 명령어들을 작성하세요:

---

## 8\. 보너스 문제

### 8-1. 한 줄 명령어 도전

\# 모든 이미지 파일을 images 디렉터리로 이동하고, 

\# 모든 문서 파일을 docs 디렉터리로 이동하는 작업을 

\# 한 줄의 명령어로 실행하세요 (세미콜론 또는 && 사용)

\# 명령어를 작성하세요:

### 8-2. 조건부 실행

\# images 디렉터리가 존재하면 모든 .jpg 파일을 이동하고,

\# 존재하지 않으면 디렉터리를 생성한 후 이동하는 명령어를 작성하세요

\# 명령어를 작성하세요:

### 8-3. 파일 개수 확인 후 실행

\# .txt 파일이 5개 이상 있으면 backup 디렉터리로 복사하고,

\# 그렇지 않으면 "파일이 부족합니다" 메시지를 출력하세요

\# 명령어를 작성하세요:

---

## 9\. 검증 명령어

각 문제를 해결한 후 다음 명령어들로 결과를 확인하세요:

\# 디렉터리 구조 확인

ls \-la

\# 특정 디렉터리 내용 확인

ls \-la backup/

ls \-la images/

ls \-la documents/

\# 파일 개수 확인

ls \*.txt | wc \-l

ls \*.jpg | wc \-l

\# 전체 파일 목록 확인

find . \-type f | sort

---

## 10\. 주의사항

⚠️ **실습 시 주의사항:**

- rm 명령어 사용 시 특히 주의하세요  
- 중요한 파일은 미리 백업하세요  
- 와일드카드 패턴이 의도한 파일들만 선택하는지 먼저 `ls` 명령어로 확인하세요  
- 실제 서버에서는 더욱 신중히 실행하세요

**패턴 확인 방법:**

\# 실제 명령 실행 전에 패턴이 올바른지 확인

echo cp \*.txt backup/    \# 실제로는 실행되지 않고 명령어만 출력

ls \*.txt                 \# 선택될 파일들 미리 확인

---

## 힌트

- `{}` 중괄호 확장 활용: `mkdir {dir1,dir2,dir3}`  
- `[]` 문자 범위 활용: `[1-3]`, `[a-z]`  
- `*` 와일드카드 활용: `file*`, `*.txt`  
- `?` 단일 문자 활용: `file?.txt`  
- 복합 패턴 활용: `*[0-9]*`, `file[1-3].txt`  
- 디렉터리 생성 시 `-p` 옵션 활용: `mkdir -p path/to/directory`

