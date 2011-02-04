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
       
Após digitar o comando acima com o e-mail utilizado para cadastro no **[GITHUB][github]**, aparecerão as seguintes mensagens: <br />
**MSG01:** "Enter file in which to save the key", onde deverá ser digitado simplesmente um nome para um arquivo onde será guardada sua chave; <br />
**MSG02:** "Enter passphrase", campo onde deverá ser digitada a senha desse arquivo e pode ser deixado em branco caso nenhuma seja necessária; <br />
**MSG03:** "Enter passphrase again", aqui, a repetição da mesma. <br /> 
       
Parabéns, seu par de chaves **RSA** foi criado. :) <br /><br />


**ESPERA! O QUE É ESSE PAR DE CHAVES RSA?** <br />
Basicamente, **RSA** é um dos mais seguros algoritmos de criptografia de dados existentes e envolve sempre um par de chaves: a pública, que pode ser conhecida e a privada, que deve ser mantida em sigilo.


## 5.0 ADICIONANDO A CHAVE EM SUA CONTA NO GITHUB
Agora que já foram criadas as chaves necessárias, precisamos adicioná-las à nossa conta no **[GITHUB][github]**. <br />
Primeiramente, vamos copiar nossa chave: navegue até a pasta onde elas foram criadas, abra o arquivo público (nomedoseuarquivo.**pub**) e copie o que no mesmo estiver escrito.
    CM02 $ ~/.ssh
    CM07 $ ls
    CM08 $ vim nomedoseuarquivoarquivo.pub

Faça seu login no site. Acesse: "ACCOUNT SETTINGS" > "SSH PUBLIC KEYS" > "ADD ANOTHER PUBLIC KEY". <br />
Escolha um nome qualquer para o campo "TÍTULO" e em "KEY" cole a **SSH-RSA** que acabou de ser copiada. 


## 6.0 TESTANDO A CONEXÃO COM O GITHUB
Aqui acontece a adição do **[GITHUB][github]** na lista de hosts conhecidos. <br />
Caso seja a primeira tentativa de conexão, faça sua autenticação digitando a senha escolhida durante o passo 4.3.
    CM09 $ ssh git@github.com


## 7.0 CONFIGURAÇÕES LOCAIS
O **GIT** necessita saber seu nome de usuário e seu e-mail para propriamente creditar seus commits. Trate de arrumá-los! :P
    CM10 $ git config --global user.name "SEU NOME DE USUÁRIO"
    CM11 $ git config --global user.email "seuemail@seudominio.com"


## 8.0 CRIANDO UM REPOSITÓRIO NO GITHUB
No site do **[GITHUB][github]**, acesse: "DASHBOARD" > "NEW REPOSITORY". Escolha um nome para o seu projeto e... pronto! <br />

**E AGORA, ONDE FICARÃO MEUS ARQUIVOS?** <br />
Criado o repositório no site, crie uma pasta com o mesmo nome em seu computador. Esse será seu repositório local.
    CM12 $ mkdir NOMEPROJETO


## 9.0 O PRIMEIRO COMMIT
Primeiramente, vá até seu repositório local e inicialize o **GIT**. 
    CM13 $ cd NOMEPROJETO
    CM14 $ git init

Utilize **CM15** para selecionar arquivos específicos ou então faça uso do **CM16** para adicionar todos os arquivos do repositório em que o **GIT** foi inicializado.
    CM15 $ git add ARQUIVO1 ARQUIVO2 ARQUIVO3
    CM16 $ git add .

Após feita a marcação de arquivos a serem enviados ao repositório (**CM15**/**CM16**), é necessário fazer uso do commit:
    CM17 $ git commit -m 'uma mensagem qualquer vem aqui'

Aponte para o repositório do **[GITHUB][github]**:
    CM18 $ git remote add origin git@github.com:nomedecadastronosite/NOMEPROJETO.git
    
E, finalmente... envie os arquivos para o servidor:
    CM19 $ git push origin master

**LEMBRETE**: NOMEPROJETO é o nome do repositório criado na seção 8.1. <br />
Os comandos **CM18**/**CM19** podem resumir-se a um único: <br />
    CM20 $ git push git@github.com:nomedecadastronosite/NOMEPROJETO.git master



[github]: http://github.com
