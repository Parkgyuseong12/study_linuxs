# 연습문제 1: 기본 파일 시스템 탐색
## 1-1. 현재 위치 확인 및 이동
### 현재 작업 디렉터 절대 경로를 출력
```
[parkgyuseong@localhost ~]$ pwd
/home/parkgyuseong
```
### 홈 디렉토리로 이동
```
[parkgyuseong@localhost ~]$ cd /home
[parkgyuseong@localhost home]$ pwd
/home
```
### 루트 디렉토리로 이동
```
[parkgyuseong@localhost home]$ cd ../..
[parkgyuseong@localhost /]$ pwd
/
```
### 다시 홈 디렉토리로 이동
```
[parkgyuseong@localhost /]$ cd /home
[parkgyuseong@localhost home]$ pwd
/home
```
### 현재 디렉터리의 파일과 폴더 목록 출력
```
[parkgyuseong@localhost home]$ ls
parkgyuseong
```
### 숨김 파일을 포함한 모든 파일의 상세정보를 출력
```
[parkgyuseong@localhost home]$ ls -l
total 4
drwx------. 14 parkgyuseong parkgyuseong 4096 Jul 16 10:54 parkgyuseong
[parkgyuseong@localhost home]$ cd ..
[parkgyuseong@localhost /]$ ls
afs  boot  etc   lib    media  opt   root  sbin  sys  usr
bin  dev   home  lib64  mnt    proc  run   srv   tmp  var
```
### /etc 디렉토리의 내용을 출력
```
[parkgyuseong@localhost /]$ cd etc
[parkgyuseong@localhost etc]$ ls
accountsservice          firewalld       makedumpfile.conf.sample  samba
adjtime                  flatpak         man_db.conf               sane.d
aliases                  fonts           mcelog                    sasl2
alsa                     foomatic        microcode_ctl             security
alternatives             fprintd.conf    mime.types                selinux
anacrontab               fstab           mke2fs.conf               services
appstream.conf           fuse.conf       modprobe.d                sestatus.conf
asound.conf              fwupd           modules-load.d            setroubleshoot
at.deny                  gcrypt          motd                      sgml
audit                    gdm             motd.d                    shadow
authselect               geoclue         mtab                      shadow-
avahi                    glvnd           multipath                 shells
bash_completion.d        gnupg           nanorc                    skel
bashrc                   GREP_COLORS     netconfig                 smartmontools
bindresvport.blacklist   groff           NetworkManager            sos
binfmt.d                 group           networks                  speech-dispatcher
bluetooth                group-          nftables                  ssh
brlapi.key               grub2.cfg       nsswitch.conf             ssl
brltty                   grub.d          nsswitch.conf.bak         sssd
brltty.conf              gshadow         nvme                      statetab.d
chromium                 gshadow-        openldap                  subgid
chrony.conf              gss             opt                       subgid-
chrony.keys              host.conf       os-release                subuid
cifs-utils               hostname        ostree                    subuid-
cockpit                  hosts           PackageKit                sudo.conf
containers               hp              pam.d                     sudoers
cron.d                   inittab         papersize                 sudoers.d
cron.daily               inputrc         passwd                    sudo-ldap.conf
cron.deny                iscsi           passwd-                   sysconfig
cron.hourly              issue           pbm2ppa.conf              sysctl.conf
cron.monthly             issue.d         pinforc                   sysctl.d
crontab                  issue.net       pkcs11                    systemd
cron.weekly              kdump           pkgconfig                 system-release
crypto-policies          kdump.conf      pki                       system-release-cpe
crypttab                 kernel          plymouth                  terminfo
csh.cshrc                keys            pm                        tmpfiles.d
csh.login                keyutils        pnm2ppa.conf              tpm2-tss
cups                     krb5.conf       polkit-1                  trusted-key.key
cupshelpers              krb5.conf.d     popt.d                    tuned
dbus-1                   ld.so.cache     printcap                  udev
dconf                    ld.so.conf      profile                   udisks2
debuginfod               ld.so.conf.d    profile.d                 updatedb.conf
default                  libaudit.conf   protocols                 UPower
depmod.d                 libblockdev     pulse                     usb_modeswitch.conf
dhcp                     libibverbs.d    qemu-ga                   vconsole.conf
DIR_COLORS               libnl           ras                       vimrc
DIR_COLORS.lightbgcolor  libpaper.d      rc.d                      virc
dnf                      libreport       rc.local                  vmware-tools
dnsmasq.conf             libssh          redhat-release            vulkan
dnsmasq.d                libuser.conf    request-key.conf          wgetrc
dracut.conf              locale.conf     request-key.d             wireplumber
dracut.conf.d            localtime       resolv.conf               wpa_supplicant
egl                      login.defs      rocky-release             X11
enscript.cfg             logrotate.conf  rocky-release-upstream    xattr.conf
environment              logrotate.d     rpc                       xdg
ethertypes               lsm             rpm                       xml
exports                  lvm             rsyncd.conf               yum
favicon.png              machine-id      rsyslog.conf              yum.conf
filesystems              magic           rsyslog.d                 yum.repos.d
firefox                  mailcap         rwtab.d
```

# 연습문제 2: 디렉터리 및 파일 생성
### practice 디렉터리 구조 생성
```
parkgyuseong@localhost ~]$ mkdir practice
[parkgyuseong@localhost ~]$ cd practice/
[parkgyuseong@localhost practice]$ mkdir documents
[parkgyuseong@localhost practice]$ mkdir images
[parkgyuseong@localhost practice]$ mkdir backup
[parkgyuseong@localhost practice]$ cd documents
[parkgyuseong@localhost documents]$ mkdir notes
[parkgyuseong@localhost documents]$ cd reports/
[parkgyuseong@localhost reports]$ mkdir ls
parkgyuseong@localhost practice]$ tree
practice
│   ├── backup
│   ├── documents
│   │   ├── notes
│   │   └── reports
│   │       └── ls
│   └── images
```

### practice/notes/ 디렉터리에 memo.txt 파일을 생성하고 "Linux 명령어 연습 중"이라는 내용을 작성
```
[parkgyuseong@localhost ~]$ cd practice/documents/notes/
[parkgyuseong@localhost notes]$ touch memo.txt
[parkgyuseong@localhost notes]$ cd memo.txt
bash: cd: memo.txt: Not a directory
[parkgyuseong@localhost notes]$ echo "Linux" > memo.txt
```
### practice/documents/ 디렉터리에 readme.txt 파일을 생성하고 "Hello Linux!"라는 내용을 작성
```
[parkgyuseong@localhost notes]$ cd ..
[parkgyuseong@localhost documents]$ touch readme.txt
[parkgyuseong@localhost documents]$ echo "Hello Linux!" > readme.txt
[parkgyuseong@localhost documents]$
```

# 연습문제 3: 파일 내용 확인 및 조작
### readme.txt 내용 출력
```
[parkgyuseong@localhost documents]$ cat readme.txt
Hello Linux!
```

### memo.txt 내용 출력
```
[parkgyuseong@localhost documents]$ cd notes
[parkgyuseong@localhost notes]$ cat memo.txt
Linux
```

### readme.txt 파일 backup/ 디렉토리로 복사
```
[parkgyuseong@localhost documents]$ cp readme.txt /home/parkgyuseong/practice/backup/
[parkgyuseong@localhost documents]$ cd ..
[parkgyuseong@localhost practice]$ cd backup/
[parkgyuseong@localhost backup]$ ls
readme.txt
```

### documents/ 디렉터리 전체를 backup/ 디렉터리에 복사
```
[parkgyuseong@localhost backup]$ cd ..
[parkgyuseong@localhost practice]$ 
[parkgyuseong@localhost practice]$ 
[parkgyuseong@localhost practice]$ pwd
/home/parkgyuseong/practice
[parkgyuseong@localhost practice]$ cp documents/ backup/
cp: -r not specified; omitting directory 'documents/'
[parkgyuseong@localhost practice]$ cp documents /home/parkgyuseong//practice/backup/
cp: -r not specified; omitting directory 'documents'
[parkgyuseong@localhost practice]$ cp -r documents /home/parkgyuseong/practice/backup/
[parkgyuseong@localhost practice]$ cd ..
[parkgyuseong@localhost ~]$ cd practice/
[parkgyuseong@localhost practice]$ cd backup/
[parkgyuseong@localhost backup]$ ls
documents  readme.txt
```

# 연습문제 4: 파일 이동 및 이름 변경
### memo.txt 파일을 documents/ 디렉터리로 이동
```
[parkgyuseong@localhost documents]$ cd notes/
[parkgyuseong@localhost notes]$ ls
memo.txt
[parkgyuseong@localhost notes]$ mv memo.txt /home/parkgyuseong/practice/documents/
[parkgyuseong@localhost notes]$ cd ..
[parkgyuseong@localhost documents]$ ls
memo.txt  notes  readme.txt  reports
```

### images/ 디렉터리를 practice/media/로 이름을 변경
```
[parkgyuseong@localhost practice]$ mv practice media
[parkgyuseong@localhost practice]$ ls
backup  documents  media
```

### readme.txt를 introduction.txt로 이름을 변경
```
[parkgyuseong@localhost practice]$ cd backup
[parkgyuseong@localhost backup]$ ls
documents  readme.txt
[parkgyuseong@localhost backup]$ mv readme.txt introducktion.txt
[parkgyuseong@localhost backup]$ ls
documents  introducktion.txt
[parkgyuseong@localhost backup]$ cd ..
[parkgyuseong@localhost practice]$ cd documents
[parkgyuseong@localhost documents]$ mv readme.txt introduce.txt
[parkgyuseong@localhost documents]$ ls
introduce.txt  memo.txt  notes  reports
```

### memo.txt를 study_notes.txt로 변경
```
[parkgyuseong@localhost practice]$ cd documents/
[parkgyuseong@localhost documents]$ ls
introduce.txt  memo.txt  notes  reports
[parkgyuseong@localhost documents]$ mv memo.txt study_notes.txt
[parkgyuseong@localhost documents]$ ls
introduce.txt  notes  reports  study_notes.txt
[parkgyuseong@localhost documents]$ 
[parkgyuseong@localhost documents]$ cd ..
[parkgyuseong@localhost practice]$ cd backup
[parkgyuseong@localhost backup]$ ls
documents  introducktion.txt
[parkgyuseong@localhost backup]$ cd documents/
[parkgyuseong@localhost documents]$ ls
notes  readme.txt  reports
[parkgyuseong@localhost documents]$ mv notes study_notes.txt
```

# 연습문제 5 종합실습
## 프로젝트 디렉토리 생성
### my_project/라는 최상위 디렉터리 생성
```
z[parkgyuseong@localhost documents]$ cd ..
[parkgyuseong@localhost backup]$ cd ..
[parkgyuseong@localhost practice]$ cd ..
[parkgyuseong@localhost ~]$ mkdir my_project
```
### 하위에 src/, docs/, tests/, config/ 디렉터리 생성
```
[parkgyuseong@localhost my_project]$ mkdir src
[parkgyuseong@localhost my_project]$ mkdir docs
[parkgyuseong@localhost my_project]$ mkdir tests
[parkgyuseong@localhost my_project]$ mkdir config
[parkgyuseong@localhost my_project]$ ls
config  docs  src  tests
```
### src/ 디렉터리에 main.py 파일 생성 (내용: "# Main Python File")
```
[parkgyuseong@localhost my_project]$ cd src
[parkgyuseong@localhost src]$ pwd
/home/parkgyuseong/my_project/src
[parkgyuseong@localhost src]$ touch main.py
[parkgyuseong@localhost src]$ echo "#Main Python File" > main.py
[parkgyuseong@localhost src]$ ls
main.py
```

### docs/ 디렉터리에 README.md 파일 생성 (내용: "# My Project Documentation")
```
[parkgyuseong@localhost src]$ cd ..
[parkgyuseong@localhost my_project]$ cd docs
[parkgyuseong@localhost docs]$ touch README.md
[parkgyuseong@localhost docs]$ echo "#My Project Documentation" > README.md 
[parkgyuseong@localhost docs]$ ls
README.md
```

### config/ 디렉터리에 settings.conf 파일 생성 (내용: "# Configuration File")
```
[parkgyuseong@localhost docs]$ cd ..
[parkgyuseong@localhost my_project]$ cd config/
[parkgyuseong@localhost config]$ touch settings.conf
[parkgyuseong@localhost config]$ echo "#Configuration File" > settings.conf
[parkgyuseong@localhost config]$ ls
settings.conf
```
# 5-2. 백업 및 정리
## 전체 my_project/ 디렉터리를 my_project_backup/으로 복사
```
[parkgyuseong@localhost ~]$ cp -r my_project my_project_backup
[parkgyuseong@localhost ~]$ ls
Desktop    Downloads  my_project         Pictures  Public     Videos
Documents  Music      my_project_backup  practice  Templates
```

### my_project/src/main.py 파일을 my_project/src/app.py로 이름을 변경하시오.
```
[parkgyuseong@localhost ~]$ mv my_project/src/main.py my_project/src/app.py
[parkgyuseong@localhost ~]$ cd my_project/src/
[parkgyuseong@localhost src]$ ls
app.py
```

### my_project/docs/README.md 파일을 my_project/ 디렉터리로 이동
```
[parkgyuseong@localhost src]$ cd ..
[parkgyuseong@localhost my_project]$ cd ..
[parkgyuseong@localhost ~]$ mv my_project/docs/README.md my_project
[parkgyuseong@localhost ~]$ cd my_project
[parkgyuseong@localhost my_project]$ ls
config  docs  README.md  src  tests
```










