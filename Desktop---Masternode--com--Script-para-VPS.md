**Passo a passo simplificado**

Pasta de arquivos de configuração:

MacOS - ~/Library/Application Support/ZCoreCore/

Linux - /home/user/.zcore/

Windows XP- C:\Documents and Settings\{user}\Application Data\ZCoreCore

Windows 10 - C:\Users\<user>\AppData\ZCoreCore

1. Abra a carteira
2. Abra o console de depuração - **Ferramentas > Console de Depuração**
3. Crie um novo ENDEREÇO, executando: `getnewaddress`
4. Envie 5000 zcr para o endereço criado, executando: `sendtoaddress ENDEREÇO 5000`
5. Aguarda 15 confirmações.
6. Após confirmado, volte no console de depuração, execute: `masternode genkey`
7. Também execute: `masternode outputs`

- Copie os dados do passo 6 e 7.

8. Feche a carteira.

9. Abra o arquivo masternode.conf e insira as seguintes informações:

```
nomeQualquer IP:DO:SEU:VPS:17291 PASSO_6 PASSO_7
```

Exemplo: 
```
mn1 127.0.0.2:17291 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a 0
```

Salve o arquivo.

10. No terminal da VPS, execute:
```
sudo curl -o- https://raw.githubusercontent.com/zcore-coin/masternode-auto/master/install.sh | bash
```
Siga as instruções no script.

* No final do comando será mostrado todos detalhes do Masternode, é de muita importância que você os guarde
para eventual uso.

11. Inicie sua carteira Desktop.

12. Ative a aba de masternodes - ** Configurações > Opções > Ativar aba de masternode **

13. Volte a tela principal e abra a aba de masternodes.

14. Selecione seu masternode e clique em start-alias.


Inicialmente ficará PRE-ENABLED.

Posteriormente mudará para ENABLED. Leva cerca de 1-2 horas.

Dependendo da condição da VPS, ela pode vir a ter o status EXPIRED,

Clique novamente em start-alias e caso ocorra o mesmo erro, feche a carteira e apague o arquivo mnpayments.dat na pasta de configuração.

Tente novamente clicar em start-alias. Se o problema persistir, refaça os procedimentos de criação.

