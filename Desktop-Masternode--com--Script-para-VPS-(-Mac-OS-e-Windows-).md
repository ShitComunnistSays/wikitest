#### Passo a passo simplificado

#### Encontre a pasta com arquivos de configuração, de acordo com seu sistema operacional:

https://github.com/zcore-coin/zcore-source/wiki

#### 1. Siga os passos na carteira desktop:
1. Abra o console de depuração - **Ferramentas > Console de Depuração**
2. Crie um novo ENDEREÇO, executando: `getnewaddress`
3. Envie 5000 zcr para o endereço criado, executando: `sendtoaddress ENDEREÇO 5000`
4. Aguarda 15 confirmações.
5. Após confirmado, volte no console de depuração, execute: `masternode genkey`
6. Também execute: `masternode outputs`

- Copie os dados do passo 5 e 6.

7. Feche a carteira.

8. Abra o arquivo **masternode.conf** (pasta encontrada anterior ao passo 1), e insira as seguintes informações:

```
nomeQualquer IP:DO:SEU:VPS:17291 PASSO_5 PASSO_6
```

Exemplo: 
```
mn1 127.0.0.2:17291 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a 0
```

* Salve o arquivo.

#### 10. Siga os passos no terminal da VPS, inicie o script executando:
```
sudo curl -o- https://raw.githubusercontent.com/zcore-coin/masternode-auto/master/install.sh | bash
```

* Siga as instruções do script.
* No final do comando será mostrado todos detalhes do Masternode, é de muita importância que você os guarde
para eventual uso.

11. Inicie sua carteira Desktop.

12. Ative a aba de masternodes - **Configurações > Opções > Ativar aba de masternode**

13. Volte a tela principal e abra a aba de masternodes.

14. Selecione seu masternode e clique em start-alias.

#### NOTA

Inicialmente ficará PRE-ENABLED.

Posteriormente mudará para ENABLED. Leva cerca de 1-2 horas.

Dependendo da condição da VPS, ela pode vir a ter o status EXPIRED,

Clique novamente em start-alias e caso ocorra o mesmo erro, feche a carteira e apague o arquivo mnpayments.dat na pasta de configuração.

Tente novamente clicar em start-alias. Se o problema persistir, refaça os procedimentos de criação.

