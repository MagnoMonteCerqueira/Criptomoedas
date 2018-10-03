


![Alt Text](https://github.com/MagnoMonteCerqueira/Altcoins/blob/master/src/imgs/explorer.jpg)

##                                      Tutorial de instalação Explorer para Altcoins com banco de dados MongoDB!


## Introdução.

Uma criptomoeda (um tipo de moeda Digital descentralizada) é um meio de troca que se utiliza da tecnologia de blockchain e da criptografia para assegurar a validade das transações e a criação de novas unidades da moeda. O Bitcoin, a primeira criptomoeda descentralizada, foi criado em 2009 pelo pseudônimo Satoshi Nakamoto. Desde então, muitas outras criptomoedas foram criadas. Mais recentemente, temos assistido a um fenómeno de explosão de inúmeros tokens que têm sido criados com base no protocolo do Ethereum, principalmente após a onda massiva de Ofertas Iniciais de Moedas (usualmente referida como ICO, do inglês Initial Coin Offering) que ocorreu em 2017.

Ao contrário de sistemas bancários centralizados, grande parte das criptomoedas usam um sistema de controle descentralizado com base na tecnologia de blockchain, que é um tipo de livro-registro distribuído operado em uma rede ponto-a-ponto (peer-to-peer) de milhares computadores, onde todos possuem uma cópia igual de todo o histórico de transações, impedindo que uma entidade central promova alterações no registro ou no software unilateralmente sem ser excluída da rede.


## Requisitos:

Servidor Ubuntu 16 (x64), Apache2, MongoDB.


## Instalação.

##
###### 1) Vamos acessar o servidor via ssh ou interface grafica e atualizar o repositório como root:

```sh
$ apt-get update
```
##
###### 2) Para a instalação do Explorer é necessário instalar os pacotes e dependencias:

```sh
# apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git apache2

# apt-get install nodejs-legacy npm libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev 

# apt-get install libboost-test-dev libboost-thread-dev libdb4.8-dev libdb4.8++-dev libminiupnpc-dev libzmq3-dev 

# apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler

# apt-get install software-properties-common && add-apt-repository ppa:bitcoin/bitcoin && apt-get update

# npm install forever -g

```

##
###### 3)  Após todos os passos anteriores, vamos instalar o banco de dados:

```sh
# apt-key adv --keyserver hkp: //server.ubuntu.com: 80 --recv EA312927

# echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list

# apt-get update

# apt-get install -y mongodb-org

# systemctl daemon-reload

# systemctl start mongod

# systemctl enable mongod

# netstat -plntu

# mongo

# use bancodacoin

# db.createUser( { user: "biticaouser", pwd: "biticaosenha", roles: [ "readWrite" ] } )

# exit
```

##
###### 4)  Apos banco de dados criado e usuario para acesso do explorer e hora de fazer donwload do Explorer via GitHub:

```sh
# cd /var/www/

# git clone https://github.com/iquidus/explorer explorer

# cd explorer && npm install --production

# cp ./settings.json.template ./settings.json 
```

##
###### 5)  Vamos editar o arquivo de configuração do Explorer e inserir as informações abaixo:


##### Alterar linha 8 - "title"
```sh
# "title": "Explorer Biticao", 
```
##### Alterar linha 10 - IP (vamos manter padrao)
```sh
# "address": "127.0.0.1:3002",
```
##### Alterar linha 13 - (Nome da moeda)
```sh
# "coin": "BitiCao",
```
##### Alterar linha 16 - (Símbolo da moeda)
```sh
# "symbol": "BTC",
```
##### Alterar Linha 19 - Alterar imagem no repositório (logo.png)
```sh
# "logo": "/images/logo.png",
```
##### Alterar Linha 22 - Alterar imagem no repositório (favicon.ico)
```sh
# "favicon": "public/favicon.ico",
```
##### Na linha 29 escolha o tipo de (theme)
###### Obs: pode utilizar os temas abaixo:
###### Cerulean, Cosmo, Cyborg, Darkly, Flatly, Journal, Lumen, Paper,Readable, Sandstone, Simplex, Slate, Spacelab, Superhero, United, Yeti
```sh
# "theme": "Cyborg",
```
##### Na linha 35 até a 41 esta os dados do banco
```sh
# "user": "biticaouser",

# "password": "biticaosenha",

# "database": "biticaodb",

# "address": "localhost",

```

##### Alterar Linha 49 a 52 - Host, Porta, Usuario e Senha da Wallet.
```sh
# "host": "localhost",

# "port": 123456789,

# "user": "biticao_rpc",

# "pass": "biticaosenhaforte"

```

##### Alterar da Linha 63 a 71 - Api, markets, richlist, twitter, facebook, googleplus, pesquisa, movimento, rede.
```sh
# "api": true,

# "markets": true,

# "richlist": true,

# "twitter": true,

# "facebook": false,

# "googleplus": false,

# "search": true,

# "movement": true,

# "network": true

```


##### Alterar da Linha 83 a 86 - vamos seguir os passos abaixo:
```sh
# "blockindex": 1337,

# "blockhash": "1733320247b15ca2262be646397d1ffd6be953fa638ebb8f5dcbb4c2b91b34f1",

# "txhash": "f270cd3813254c9922a2e222a56ba745842d9112223a1394062e460b33d27b7e",

# "address": "RBiXWscC63Jdn1GfDtRj8hgv4Q6Zppvpwb"

```





