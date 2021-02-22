#https://stackoverflow.com/questions/11542846/nvm-node-js-recommended-install-for-all-users

Login as root: sudo -s
Install nvm: curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh |   NVM_DIR=/usr/local/nvm bash
Created a file called nvm.sh in /etc/profile.d with the following contents: #!/usr/bin/env bash
export NVM_DIR="/usr/local/nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
Run /etc/profile.d/nvm.sh
Install node: nvm install node
Optionally update npm with: npm install -g npm
