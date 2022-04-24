## Chaves ssh##

Forma segura de se conectar em um host linux e mais conveniente.
	Ex: Forma convencional de se conectar em um server:
	       -> ssh <username>@<ipadrress>
                    colocar senha e se conectar

Conectando via chave ssh você evita ter que ficar digitando toda vez a senha. E caso tenha algum malware,hacker, em seu sistema, ele vai captar a senha que você digitou para se conectar ao host, e vai ter acesso. Assim que se cria uma chave ssh é pedido para digitar a passphrase, uma senha basicamente, para caso alguem "roube" sua chave a "passphrase" é uma  camada de seguranca a mais. 

Como funciona a conexao via chave SSH. -> Quando se gera uma chave ssh são gerados dois arquivos: Chave publica e chave privada. A chave PRIVADA não pode, em hipotese NENHUMA ser mostrada,vazada,copiada..etc. Já a chave publica, como o nome já diz, é publica e é utilizada para fazer o "match" da chave PRIVADA que está em sua máquina, com a chave publica que TEM que ser colocada dentro do host remoto no arquivo ~/.ssh/authorized_keys

Criar uma chave ssh e add ao servidor remoto e desabilitar o password auth.


Command -> ssh-keygen -t ed25519 -C "acme"


Copiar a chave publica para o host
	-> ssh-copy-id -i ~/.ssh/<public_key.pub> <user>@<remote_host_to_add_key>
