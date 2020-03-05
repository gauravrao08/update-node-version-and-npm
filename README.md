# update-node-version-and-npm

https://nodejs.org/en/download/releases/

```
npm cache clean -f
npm install -g n
npm install -g npm@5.6.0    ## npm 5.6.0 is the new version of npm which is required to respective nodejs version

sudo n 9.4.0   ## new nodejs version you want to install

n   ##check the 'n' command drop down and up arrow to check the version of node js

[root@ip bin]# pwd
/usr/bin
[root@ip bin]# ./node  -v
v11.15.0
[root@ip bin]# mv node node_old
[root@ip bin]# cp -r //usr/local/bin/node .
[root@ip bin]# ./node -v
v10.13.0
[root@ip bin]# npm -v
6.4.1

```
