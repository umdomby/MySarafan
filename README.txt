# MySarafan
# sarafan

Перед началом работы необходимо настроить рабочее место и установить на компьютер node js и Yarn.

..yarn
https://classic.yarnpkg.com/en/docs/install#centos-stable
//Install yarn CentOS / Fedora / RHEL
curl --silent --location https://dl.yarnpkg.com/rpm/yarn.repo | sudo tee /etc/yum.repos.d/yarn.repo
curl --silent --location https://rpm.nodesource.com/setup_12.x | sudo bash -
sudo yum install yarn
## OR ##
sudo dnf install yarn
//Install yarn Ubuntu
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update && sudo apt install yarn
sudo apt update && sudo apt install --no-install-recommends yarn
yarn --version

..Node
//Ссылка на видео по установке Node.js:
https://youtu.be/ZNjnM0Fyn4E
https://github.com/nvm-sh/nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
Close console or:
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
nvm ls
nvm install stable
nvm install lts/carbon
nvm use stable

..npm
instal npm
https://www.youtube.com/watch?v=TsM4Mekj_54
npm init
cat package.json
npm install --save lodash
cat package.json
npm i --save react
npm i --save-dev http-server
./node_modules/http-server/bin/http-server
//add package.json --> "http-server": "./node_modules/http-server/bin/http-server",
npm run http-server

//delete package
npm un loadash

npm shrinkwrap
//glabal package
npm i -g create-react-app
cd sweater
create-react-app sweater-app
cd sweater-app/
ll
//delete global package
sudo npm un -g create-react-app

cd sweater
npm outdated
npm update


https://losst.ru/ustanovka-node-js-ubuntu-18-04
sudo apt install nodejs
sudo apt install npm


#npm run sweater-app

..set webpack
//Terminal Intellij Idea
yarn init
yarn add vue vue-resource
yarn add -D webpack webpack-cli webpack-dev-server babel-loader @babel/core @babel/preset-env vue-loader vue-template-loader
//add --> package.json
  "scripts": {
    "start": "webpack-dev-server --config webpack.dev.js",
    "build": "webpack --config webpack.prod.js"
  },


sudo lsof -i :8000
ps aux | grep node

kill -9






Main - RestController

// GET all
fetch('/message/').then(response => response.json().then(console.log))

// GET one
fetch('/message/2').then(response => response.json().then(console.log))

// POST add new one
fetch(
  '/message', 
  { 
    method: 'POST', 
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ text: 'Fourth message (4)', id: 10 })
  }
).then(result => result.json().then(console.log))

// PUT save existing
fetch(
  '/message/4', 
  { 
    method: 'PUT', 
    headers: { 'Content-Type': 'application/json' }, 
    body: JSON.stringify({ text: 'Fourth message', id: 10 })
  }
).then(result => result.json().then(console.log));

// DELETE existing
fetch('/message/4', { method: 'DELETE' }).then(result => console.log(result))

//postman
{
    "text": "Fourth message (21231)"
}
