Os procedimentos são simples, não há muito segredo.

### Windows 

1. Faça backup do arquivo que contém suas zcores ( wallet.dat )

2. Feche a carteira

3. Instale o novo cliente do site ou github.

4. Abra a carteira. ( atualizado )


### Linux

1. Faça backup do arquivo que contém suas zcores ( wallet.dat )

2. Feche a carteira, execute:

  `zcore-cli stop`

3. Instale o novo cliente, execute no terminal:

   `cd ~/`

   `mkdir ~/zcore`

   `cd zcore`

   `git clone https://github.com/zcore-coin/zcore-source .`

   `./autogen.sh`

   `./configure --with-gui=no --disable-tests --disable-gui-tests`

   `make`

   `make install`

4. Abra a carteira. ( atualizado )
  `zcored -daemon`