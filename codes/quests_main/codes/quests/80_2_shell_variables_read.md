### 인자와 read를 함께 사용하여 변수 조합 출력

```
[parkgyuseong@localhost quests]$ nano 80_2_shell_variables_read.sh

name="$1"
read -p "read input : " read1
echo "input value :" "$1" "$read1"
```

```
[parkgyuseong@localhost quests]$ source 80_2_shell_variables_read.sh agument_first
read input : read_first
input value : agument_first read_first


```
.