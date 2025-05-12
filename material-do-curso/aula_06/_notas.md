# 06 - SCRIPT DE PHP EXECUTÁVEL DENTRO DO SERVIDOR LINUX

Como podemos transformar um script de PHP num executável dentro de um servidor linux?
Tradicionalmente o PHP está associado a servidores Linux.
É nesse ambiente que faz mais sentido saber como podemos criar um executável a partir
de um script de PHP. O objetivo é que o script seja autosuficiente quando se pretende
executá-lo, independentemente do local onde o estamos a executar.

Temos um servidor Linux Ubuntu com o PHP 8.1 instalado.

Necessitamos saber onde está instalado o PHP.

which php

Agora, vamos criar um script de PHP usando o editor nano.
sudo nano script.php

#!/usr/bin/php
<?php
echo "Olá Mundo!";

Agora temos um script.php dentro da pasta do user.
A primeira linha vai indicar o caminho completo dentro do servidor onde existe o executável do PHP.
Agora o nosso script pode ser transformado num executável, ou melhor, num script que pode ser
executado sem que tenhamos que lhe indicar onde está o interpretador do PHP.
Foi o que indicámos dentro do próprio script.

Vamos mudar o chmod do script para X

sudo chmod +x script.php

Agora podemos ver que o nosso script ficou com uma cor diferente.
Vamos executá-lo.

./script.php

Podemos agora adicionar qualquer lógica de programação dentro do script e ele vai ser executado em qualquer lugar.

Vamos criar uma pasta e mover o script para o seu interior

sudo mkdir teste
sudo mv script.php teste
cd teste
./script.php

