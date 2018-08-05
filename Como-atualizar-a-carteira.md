Os procedimentos são simples, mas requer atenção.

### Procedimento de backup

https://github.com/zcore-coin/zcore-source/wiki/Como-fazer-backup


### VPS do Masternode

Se você for atualizar a VPS do Masternode, depois de ter usado o script:

https://github.com/zcore-coin/masternode-auto

Siga os passos:

1. Inicialmente logue no usuário root: `su root`

2. Pare o serviço de masternode: `systemctl stop worker01.service`

3. Rode os comandos:
```
wget https://github.com/zcore-coin/zcore-source/releases/download/v1.6.0/zcore-1.6.0-x86_64-linux.tar.gz

tar -xzvf zcore-1.6.0-x86_64-linux.tar.gz

cd zcore-1.6.0/

cp * /usr/local/ -a
```

4. Inicie o serviço de masternode:

`systemctl start worker01.service`

Não é necessário seguir os passos abaixo para Linux.

### Windows 

1. Feche a carteira

2. Instale o novo cliente do site ou github.

3. Abra a carteira nova. ( atualizado )

4. Faça um atalho a partir do arquivo 'zcore-qt.exe',
 em uma das seguintes pastas:
 
Local de instalação para sistema operacional x64

`C:\Program Files\ZCoreCore\`

Local de instalação para sistema operacional x86

`C:\Program Files (x86)\ZCoreCore\`

### Linux

1. Feche a carteira, execute:

  `zcore-cli stop`

2. Instale o novo cliente, execute no terminal:

   `wget https://github.com/zcore-coin/zcore-source/releases/download/v1.6.0/zcore-1.6.0-x86_64-linux.tar.gz`

   `tar -xzvf zcore-1.6.0-x86_64-linux.tar.gz`

   `cd zcore-1.6.0/`

   `cp * /usr/local/ -a`

3. Abra a carteira. ( atualizado )

   `zcored`

   `zcore-cli getinfo`
