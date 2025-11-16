---
Заметки: true
Приоритет: 0
Интерес: 0
Обложка: https://upload.wikimedia.org/wikipedia/commons/thumb/b/b5/Termux.svg/1200px-Termux.svg.png
tags:
---

pkg update
pkg upgrade
pkg install git
pkg install wget

```
git config --global core.compression 0
```

```
git config --global core.quotepath false
```

```
cd /storage/emulated/0/Documents/Obsidian
```

```
apt update && 
apt upgrade
```

```
git fsck --full &&
git fsck --name-objects
```

```
git pull --rebase
```

```
git reset --hard origin/main &&
git pull --rebase
```

find .git/objects/ -size 0 -delete

find .git/objects/ -type f -empty | xargs rm

git clean -f -d -n


---

- Nmap
- Curl
- 

> Termux (Android)
pkg update
pkg upgrade
pkg install git
pkg install wget
pkg install man
apt update
apt upgrade
apt list
apt install git
curl
curl --help
curl https://booi.com
clear
rm -r -f JS/
ls -la
pwd
cd ..
cd ~
cd /
cd /mnt
cd sdcard
cd user
cd home
cd storage/emulated/0/Documents/Obsidian
termux-setup-storage
am
am | grep "d"
am start -a android.intent.action.VIEW
https://www.reddit.com/r/termux/comments/182g7np/where_do_i_find_my_things_that_i_downloaded/
ssh-keygen
cat /data/data/com.termux/files/home/.ssh/id_ed25519.pub
git clone https://github.com/andrew-semenov/JS.git
git clone git@github.com:andrew-semenov/JS.git
git config --global user.email andrew.semenov.sas@gmail.com
git config --global user.name sas
git config --global --add safe.directory /storage/emulated/0/Documents/JS
git status
git show
git diff
git add .
git add README.md
git commit -m "text"
git push
