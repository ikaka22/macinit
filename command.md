
#### Prevent mac from sleeping
caffeinate -t 3600

## redis 抓包
sudo tcpdump -i eth0 'host 127.0.0.1 and tcp port 6379' -w redis.cap

## 转换文件编码
enca -L chinese test.log
iconv -f GB2312 -t UTF8 test.log

## redis信息查看
info commandstats
echo "client list"|redis|awk '{print $2}'|cut -f 2 -d '='|cut -f 1 -d ':'|sort|uniq -c

## 查看java进程
sudo jps -mlv

## 查看线程
ps -mp 20379 -o THREAD,tid,time

## 查看gc
sudo jstat -gc 20379 250 20

## dump jvm
sudo jmap -F -dump:format=b,file=heap.bin 12345

## 打印java堆栈
sudo jstack -F 20379

## git开建一个新分支
git tag publish/0.0.1
git push origin publish/0.0.1
git checkout master
git pull origin master
git checkout -b daily/0.0.2
git rebase master

## 删除tag
git tag -d publish/0.0.2
git push origin --delete publish/0.0.2
git push origin :refs/tags/publish/0.0.2

