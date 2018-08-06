Os procedimentos são simples, mas requer atenção.

## Procedimento de backup

https://github.com/zcore-coin/zcore-source/wiki/Como-fazer-backup


## VPS de Masternode

Se você for atualizar a VPS do Masternode, depois de ter usado o script:

https://github.com/zcore-coin/masternode-auto

### Siga os passos:

1. Inicialmente logue no usuário root: 

`su root`

2. Pare o serviço de masternode: 

`systemctl stop worker01.service`

3. Instale a nova carteira com os comandos:
```
wget https://github.com/zcore-coin/zcore-source/releases/download/v1.6.0/zcore-1.6.0-x86_64-linux.tar.gz

tar -xzvf zcore-1.6.0-x86_64-linux.tar.gz

cd zcore-1.6.0/

cp * /usr/local/ -a
```

4. Inicie o serviço de masternode:

`systemctl start worker01.service`

Não é necessário seguir os passos abaixo para Linux.

***



## Windows 

1. Feche a carteira

2. Instale a carteira através do site ou github.

3. Inicie a carteira nova. ( atualizado )

4. Faça um atalho a partir do arquivo 'zcore-qt.exe',
 em uma das seguintes pastas:
 
Local de instalação para sistema operacional x64

`C:\Program Files\ZCoreCore\`

Local de instalação para sistema operacional x86

`C:\Program Files (x86)\ZCoreCore\`

***


## Linux

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

4. Se for uma carteira de um Masternode, não esqueça de inicia-lo:

 a. caso não estiver configurado através da carteira do seu computador local:

   `zcore-cli masternode start-all`

 b. caso estiver configurado através da carteira do seu computador local:

   1. Abra a aba de masternodes

   2. Selecione o masternode a ser iniciado

   3. Inicie-o clicando em start-alias

***



### FAQ

1. Devo fazer backup 'apenas' antes de atualizar ?
```
R: Não! é de suma importância sempre manter o backup atualizado. Com o tempo sua carteira acrescenta muitas novas informações, então o backup antigo já não pode conter essas novas informações, o que pode levar a perda de saldo no momento de usar o backup.
 
A: Sempre use o backup mais recente.
```

2. Preciso fazer backup de quais arquivos?

```
R: É necessário fazer backup do arquivo wallet.dat, esse arquivo é o único que mantém seus saldos e apenas usando ele que pode controlar todo seu ZCore.
   Caso sua carteira local conter configuração para masternodes, faça backup do arquivo masternode.conf.
 
A: Guarde backup do arquivo wallet.dat, e se houver masternodes, também guarde o arquivo masternode.conf.
```

3. Após atualizar a carteira é preciso substituir usando o backup?
```
R: Não há necessidade, mas aconselhamos separar uma pasta nova para o backup da nova atualização.
```

4. Iniciei o masternode e ficou como EXPIRED, o que fazer?
```
R: Esse status ocorre por diversos motivos, mas é normal quando há atualização, poís você precisa fechar a carteira do seu masternode levando ao status citado.
   Você pode tentar iniciá-lo, caso o mesmo continue, é preciso recria-lo. 
   Portanto, se houver a continuação, apague o arquivo 'mnpayments.dat' ( encontrado na pasta ZCoreZCore em AppData no windows ou em .zcore no linux ) e crie novamente o masternode.
```