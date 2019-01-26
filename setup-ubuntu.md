# Prerequisites
- Nvm
- Node **8.9.0**
- Erlang/OTP
- MongoDB
- Postgress SQL
- RabbitMQ

### Install NVM
```sh
  $ wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
  $ export NVM_DIR=”/home/endeesa/.nvm”
  $ [ -s “$NVM_DIR/nvm.sh” ] && \. “$NVM_DIR/nvm.sh”
  $ [ -s "$NVM_DIR/bash_completion" ] && \.   "$NVM_DIR/bash_completion"
```
check with `nvm --version`

### Install Node 8.9.0
With nvm installed then run the following command
```sh
  $ nvm install 8.9.0
```
check with `node --version` and `npm --version`

### Install Erlang/OTP
```sh
  $ wget -O- https://packages.erlang-solutions.com/ubuntu/erlang_solutions.asc | sudo apt-key add -
  $ echo "deb https://packages.erlang-solutions.com/ubuntu bionic contrib" | sudo tee /etc/apt/sources.list.d/rabbitmq.list
  $ sudo apt update
  $ sudo apt -y install erlang
```
### Install MongoDB
```sh
  $ sudo apt update
  $ sudo apt install -y mongodb
```
see the full instructions in [Digital Ocean](https://www.digitalocean.com/community/tutorials/como-instalar-y-utilizar-postgresql-en-ubuntu-16-04-es)

### Install PostgressSQL
```sh
  $ sudo apt update
  $ sudo apt install postgresql postgresql-contrib
  $ sudo -u postgres createuser --interactive
```
after that te output looks like this
```
  Enter name of role to add: sammy
  Shall the new role be a superuser? (y/n) y
```
### Install RabbitMQ
```sh
  $ wget -O- https://dl.bintray.com/rabbitmq/Keys/rabbitmq-release-signing-key.asc | sudo apt-key add -
  $ wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc | sudo apt-key add -
  $ echo "deb https://dl.bintray.com/rabbitmq/debian $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/rabbitmq.list  
  $ sudo apt update
  $ sudo apt -y install rabbitmq-server
```
You can confirm if the service is configured to start on boot using the command:
```sh
  $ systemctl is-enabled rabbitmq-server.service
  **enabled**
```
