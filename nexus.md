```
https://levelup.gitconnected.com/deploying-private-npm-packages-to-nexus-a16722cc8166

Install NPM & Nodejs

curl –sL https://rpm.nodesource.com/setup_10.x | sudo bash -

 yum install –y nodejs
 
npm --version
6.14.10


node --version
v10.23.1

1. Create New Repo for npm-proxy
Select npm-proxy and
create repo name as same “npm-proxy”
Remote Storage as “https://registry.npmjs.org/”


mkdir nodejs
cd nodejs

#it will create  file as .npmrc under home directory /home/deployer and registory details
npm config set registry http://locahost:8081/repository/npm-proxy

cd ..
 cat .npmrc
registry=http://locahost:8081/repository/npm-proxy

#it will create package.json file
cd nodejs
npm init -y

#Modify package.json i.e remove index.js and add dependencies

{
  "name": "nodejs",
  "version": "1.0.0",
  "description": "My first nodejs package",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "dependencies": {
    "commonjs": "0.0.1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}

link :  https://stackoverflow.com/questions/57279087/authentication-error-on-publishing-to-private-npm-repository-on-nexus
allow ==> realms --> Bearer Token Realm
# npm login 

#Run COmmand to install commonjs dependencies
npm install

#Now run again the same command, this time it will run faster as it will pick from proxy

#Browser to npm-proxy in nexus and see the package installed there

```

```
2. Create new Repo npm-hosted
Select npm-hosted and
create repo name as same “npm-hosted”

#go to Server
under nodejs folder create another folder npm-app1
mkdir npm-app1
cd npm-app1
npm init -y
touch index.js

#Modify package.json to add registry

{
  "name": "npm-app1",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "publishConfig": {
     "registry": "http://locahost:8081/repository/npm-hosted/"
},
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}


#NOw we have to run the login command and enter the details of user
npm login --registry=http://localhost:8081/repository/npm-hosted/

#Now check the npmjs file with user details in encrypted format
cat ../../.npmrc
registry=http://localhost:8081/repository/npm-proxy
//localhost:8081/repository/npm-hosted/:_authToken=NpmToken.f4f6cedd-e677-3e56-bbfb-6192e21a3b39

Now run

npm publish
```
