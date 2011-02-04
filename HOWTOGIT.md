# GIT & GITHUB - OMGWTFBBQ!!1? <br />
**howto by anna**: <anna.claudia@gmail.com>
## 1.0 INTRODUÇÃO
Aparências enganam. Entender e manipular arquivos com o **GIT** é mais fácil do que aparenta. <br />
A idéia desse **HOWTO** foi reunir os passos essenciais para o funcionamento do **GIT**. Assim, podemos nos adaptar aos comandos iniciais e posteriormente incentivar outros grupos a ficarem mais influentes com os commits. :) <br />
Let's get started!


## 2.0 AFINAL, O QUE É O GIT?
**GIT** é um **SOFTWARE LIVRE** para controle de versão **DISTRIBUÍDO**. O que significa dizer que mesmo com um fluxo de trabalho centralizado, cada usuário tem um backup completo do servidor principal. Tudo é **LOCAL**. <br /><br />

**GIT É RÁPIDO, LEVE E FÁCIL DE APRENDER!** <br />
E, só pra constar... procurem quem foi o desenvolvedor do **GIT**! :D


## 3.0 PRIMEIROS PASSOS
Instale o **GIT** e crie uma conta no **[GITHUB][github]**:
    CM01 $ sudo apt-get install git-core git-doc git-gui


## 4.0 GERANDO UMA CHAVE SSH (SECURE SHELL)
**O QUÊ?!** <br />
**SSH** é um protocolo de rede que permite que dados sejam trocados entre redes diversas através de um canal seguro. <br /><br />


**ALGUMAS PRECAUÇÕES** <br />
Primeiramente, devemos checar a existência de chaves em nosso computador para que outras, porventura, não as venham sobrepor. <br />
Navegue até a pasta mostrada em **CM02**. Caso o diretório não for encontrado, sem problemas, simplesmente crie-o. Caso contrário, remova os arquivos existentes no mesmo caso tenha certeza não serem necessários. 
    CM02 $ cd ~/.ssh
    
Aqui, um **CUIDADO** especial: na pasta em questão são utilizadas chaves com nomes padrão! Portanto, um backup é muito bem-vindo em caso de dúvidas (**CM03**/**CM06**).
    CM03 $ ls
    CM04 $ mkdir key_backup
    CM05 $ cp id_rsa* key_backup
    CM06 $ rm id_rsa*
<br />


**FINALMENTE, COMO GERAR MINHA CHAVE?** <br />
**NOTA**: esse passo pode ser pulado caso alguma chave já existente vá ser utilizada.

Agora que temos certeza de que o **SSH** não vai utilizar uma chave pré-existente, podemos criar novas. <br />
Navegue até a pasta mostrada em **CM02** e utilize o comando **CM07**:
    CM07 $ ssh-keygen -t rsa -C "seuemail@seudominio.com"
       
Após digitar o comando acima com o e-mail utilizado para cadastro no **[GITHUB[github]**, aparecerão as seguintes mensagens: <br />
**MSG01** "Enter file in which to save the key", onde deverá ser digitado simplesmente um nome para um arquivo onde será guardada sua chave; <br />
**MSG02** "Enter passphrase", campo onde deverá ser digitada a senha desse arquivo e pode ser deixado em branco caso nenhuma seja necessária (é dever de todo internauta utilizar uma boa senha!); <br />
**MSG03** "Enter passphrase again", aqui, a repetição da mesma. <br /> 
       
Parabéns, seu par de chaves **RSA** foi criado. :) <br />


**ESPERA! O QUE É ESSE PAR DE CHAVES RSA?** <br />
Basicamente, **RSA** é um dos mais seguros algoritmos de criptografia de dados existentes e envolve sempre um par de chaves: a pública, que pode ser conhecida e a privada, que deve ser mantida em sigilo.


[github]: http://github.com
