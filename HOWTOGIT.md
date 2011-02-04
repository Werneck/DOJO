GIT & GITHUB OMGWTFBBQ!!1? P1
--------------------------------------
HOWTO BY ANNA <anna.claudia@gmail.com>


## 1.0 INTRODUÇÃO
    Aparências enganam. Entender e manipular arquivos com o GIT é mais fácil do que aparenta. <br />
    A idéia desse HOWTO foi reunir os passos essenciais para o funcionamento do GIT. Assim, podemos nos adaptar aos comandos iniciais e posteriormente incentivar outros grupos a ficarem mais influentes com os commits. :) <br />
    Let's get started!


## 2.0 AFINAL, O QUE É O GIT?
GIT é um SOFTWARE LIVRE para controle de versão DISTRIBUÍDO. O que significa dizer que mesmo com um fluxo de trabalho centralizado, cada usuário tem um backup completo do servidor principal. Tudo é LOCAL. <br />
GIT É RÁPIDO, LEVE E FÁCIL DE APRENDER!

"Cada diretório de trabalho é um repositório com todos os históricos e habilidade total de controle das revisões não dependente de acesso a uma rede ou a um servidor central."

<pre><code>## 2.1 PUXANDO O SACO
                <pre><code>Só pra constar, procurem quem foi o desenvolvedor do GIT! :D</code></pre>
</code></pre>

3.0 PRIMEIROS PASSOS
    3.1 INSTALAÇÃO 
        CM01 $ sudo apt-get install git-core git-doc git-gui
        
    3.2 INICIAÇÃO
        Crie uma conta no GITHUB.
        
        
4.0 GERANDO UMA CHAVE SSH (SECURE SHELL)
    4.1 O QUÊ?
        SSH é um protocolo de rede que permite que dados sejam trocados entre redes diversas através de um canal seguro.
        
    4.2 ALGUMAS PRECAUÇÕES
        Primeiramente, devemos checar a existência de chaves em nosso computador para que outras, porventura, não as venham sobrepor. 
        Navegue até a pasta mostrada em CM02. Caso o diretório não for encontrado, sem problemas, simplesmente crie-o. Caso contrário, remova os arquivos existentes no mesmo caso tenha certeza não serem necessários. 
        Aqui, um CUIDADO especial: na pasta ~/.ssh são utilizadas chaves com nomes padrão! Portanto, um backup é muito bem-vindo em caso de dúvidas (CM03/CM06).
        
       CM02 $ cd ~/.ssh
       
       CM03 $ ls
       CM04 $ mkdir key_backup
       CM05 $ cp id_rsa* key_backup
       CM06 $ rm id_rsa*
       
    4.3 FINALMENTE, COMO GERAR MINHA CHAVE?
       NOTA: esse passo pode ser pulado caso alguma chave já existente vá ser utilizada.
       
       Agora que temos certeza de que o SSH não vai utilizar uma chave pré-existente, podemos criar novas. 
       Navegue até a pasta mostrada em CM02 e utilize o comando CM07:
       CM07 $ ssh-keygen -t rsa -C "seuemail@seudominio.com"
       
       Após digitar o comando acima com o e-mail utilizado para cadastro no GITHUB, aparecerão as seguintes mensagens:
       MSG01 "Enter file in which to save the key", onde deverá ser digitado simplesmente um nome para um arquivo onde será guardada sua chave;
       MSG02 "Enter passphrase", campo onde deverá ser digitada a senha desse arquivo e pode ser deixado em branco caso nenhuma seja necessária (é dever de todo internauta utilizar uma boa senha!);
       MSG03 "Enter passphrase again", aqui, a repetição da mesma.
       
       Parabéns, seu par de chaves RSA foi criado. :)
       
       4.3.1 ESPERA! O QUE É ESSE PAR DE CHAVES RSA?
          Basicamente, RSA é um dos mais seguros algoritmos de criptografia de dados existentes e envolve sempre um par de chaves: a pública, que pode ser conhecida e a privada, que deve ser mantida em sigilo.


5.0 ADICIONANDO A CHAVE EM SUA CONTA NO GITHUB
    Agora que já foram criadas as chaves necessárias, precisamos adicioná-las à nossa conta no GITHUB.
    Primeiramente, vamos copiar nossa chave: navegue até a pasta onde foram criadas as chaves, abra o arquivo público (nomedoseuarquivo.pub) e copie o que no mesmo estiver escrito.
    
    CM02 ~/.ssh
    CM07 ls
    CM08 vim nomedoseuarquivoarquivo.pub
    
    Faça seu login no site. Acesse: "Account Settings" > "SSH Public Keys" > "Add another public key".
    Escolha um nome qualquer para o campo "Título" e em "Key" cole a SSH-RSA que acabou de ser copiada. 


6.0 TESTANDO A CONEXÃO COM O GITHUB
Aqui acontece a adição do GITHUB na lista de hosts conhecidos. 
Caso seja a primeira tentativa de conhexão, faça sua autenticação digitando a senha escolhida durante o passo 4.3.

CM09 $ ssh git@github.com


6.0 CONFIGURAÇÕES LOCAIS
O GIT necessita saber seu nome de usuário e seu e-mail para propriamente creditar seus commits. Trate de arrumá-los! :P
CM10 $ git config --global user.name "SEU NOME DE USUÁRIO"
CM11 $ git config --global user.email "seuemail@seudominio.com"


7.0 CRIANDO UM REPOSITÓRIO NO GITHUB
No site do GITHUB, acesse: "Dashboard" > "New Repository". Escolha um nome para o seu projeto e... pronto!

    7.1 E AGORA, ONDE FICARÃO MEUS ARQUIVOS?
        Criado o repositório no site, crie uma pasta com o mesmo nome em seu computador. Esse será seu repositório local.
        
        CM12 $ mkdir NOMEPROJETO


8.0 O PRIMEIRO COMMIT
Primeiramente, vá até seu repositório local e inicialize o GIT. Utilize CM15 como modelo para adição de arquivos específicos no repositório ou então faça uso do CM16 para adicionar todos os arquivos.

CM13 $ cd NOMEPROJETO
CM14 $ git init
CM15 $ git add ARQUIVO1 ARQUIVO2 ARQUIVO3
CM16 $ git add .

Após feita a marcação de arquivos a serem enviados ao repositório (CM15/CM16), é necessário fazer uso do commit:
CM17 $ git commit -m 'uma mensagem qualquer vem aqui'

Aponte para o repositório do GITHUB:
CM18 $ git remote add origin git@github.com:nomedecadastronosite/NOMEPROJETO.git
LEMBRETE: NOMEPROJETO é o nome do repositório criado na seção 7.1.
E, finalmente... envie os arquivos para o servidor:
CM19 $ git push origin master


Os comandos CM18/CM19 podem resumir-se a um único:
CM20 $ git push git@github.com:nomedecadastronosite/NOMEPROJETO.git master


9.0 BAIXANDO OUTROS ARQUIVOS (PULL)
OPTATIVO: navegue até uma pasta onde serão gravados os novos arquivos e inicialize o GIT (CM14).
Tenha em mente os nomes dos usuários e os repositórios de onde serão baixados os novos arquivos.

CM22 $ git remote add A git@github.com:nomedousuariocomarquivoslegais1/repositoriocomarquivoslegais1.git
CM23 $ git remote add B git@github.com:nomedousuariocomarquivoslegais2/repositoriocomarquivoslegais2.git
CM24 $ git remote update

Depois de feita a atualização, novos ramos (branches) que poderão ser baixados serão mostrados. Escolha-os e baixe-os:
CM25 $ git pull A nomedobranch1
CM26 $ git pull B nomedobranch5718

    9.1 OMG, MERGE CONFLICTS! E AGORA?
        Mesclar ou não mesclar, eis a questão! Sem pânico.
        
        SEM MERGE: para ignorar as mudanças, só é necessário limpar o índice de entradas. Permanecem os arquivos originais.
        CM27 $ git reset
        
        COM MERGE: o GIT marcará os conflitos na árvore de trabalho. Edite o que for necessário e adicione os arquivos editados ao contexto.
        CM28 $ git add arquivomodificado1
        CM29 $ git add arquivomodificado2
        
        Compartilhe as mudanças. Aqui é só remover os marcadores # das linhas que serão enviadas como comentários. :)
        CM30 $ git commit -a
        
        Problema resolvido!
        NOTA: os conflitos com o merge podem ser inicialmente assustadores, mas nada que não possa ser resolvido com a ajuda de algumas ferramentas interessantes. :)
        CM31 $ git mergetool
        CM32 $ git diff


NOTA: o comando abaixo informa quais os branches disponíveis:
CM33 $ git branch -r

NOTA: entender como realmente funciona o merge é uma questão de prática. Então... pratique!

NOTA: cada pasta inicializada conterá seu arquivo de configuração e este pode ser acessado utilizando-se CM28.
CM34 $ vim .git/config 

10.0 CONSIDERAÇÕES FINAIS
That's all folks! Obrigada por ler. :)

11.0 REFERÊNCIAS E OUTROS SITES INTERESSANTES
ST01 www.akitaonrails.com/2008/10/02/entendendo-git-e-instalando-gitorious-git-via-web
ST02 http://weblog.masukomi.org/2008/07/12/handling-and-avoiding-conflicts-in-git
ST03 b.lesseverything.com/2008/3/25/got-git-howto-git-and-github
ST04 www.kernel.org/pub/software/scm/git/docs/user-manual.html
ST05 www.kernel.org/pub/software/scm/git/docs/everyday.html
ST06 sysmonblog.co.uk/misc/git_by_example/
ST07 help.github.com/git-cheat-sheets/
ST08 people.gnome.org/~newren/eg/
ST09 http://www.claudson.com.br/
ST10 git.oz.cz/course/svn.html
ST11 mono-project.com/GitFAQ
ST12 help.github.com


12.0 POST-SCRIPTUM
A seção 11.0 não está ali só de enfeite. Aproveitem!:P
      