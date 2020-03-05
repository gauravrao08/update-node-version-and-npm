# update-node-version-and-npm

https://nodejs.org/en/download/releases/

```
npm cache clean -f
npm install -g n
npm install -g npm@6.4.1    ## npm 6.4.1 is the new version of npm which is required to respective nodejs version

sudo n 10.13.0  ## new nodejs version you want to install

n   ##check the 'n' command drop down and up arrow to check the version of node js

[root@ip bin]# pwd
/usr/bin
[root@ip bin]# ./node  -v   ##current version of node js
v11.15.0
[root@ip bin]# mv node node_old
[root@ip bin]# cp -r //usr/local/bin/node .
[root@ip bin]# ./node -v    ## new version of nodejs
v10.13.0
[root@ip bin]# npm -v    ##new version of npm
6.4.1

```
