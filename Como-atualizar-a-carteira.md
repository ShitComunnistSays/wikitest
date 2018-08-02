Os procedimentos são simples, não há muito segredo.

Antes é preciso fazer o procedimento de backup:

### Windows 

1. Feche a carteira

2. Instale o novo cliente do site ou github.

3. Abra a carteira. ( atualizado )


### Linux

1. Feche a carteira, execute:

  `zcore-cli stop`

2. Instale o novo cliente, execute no terminal:

   `cd ~/`

   `mkdir ~/zcore`

   `cd zcore`

   `git clone https://github.com/zcore-coin/zcore-source .`

   `./autogen.sh`

   `./configure --with-gui=no --disable-tests --disable-gui-tests`

   `make`

   `make install`

3. Abra a carteira. ( atualizado )
  `zcored -daemon`