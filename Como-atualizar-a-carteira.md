Os procedimentos são simples, mas requer atenção.

### Procedimento de backup

https://github.com/zcore-coin/zcore-source/wiki/Como-fazer-backup

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
