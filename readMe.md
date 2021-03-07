git --version => mostra a versao do git
git => mostra um monte de comando
git init => inicial o git (ramo master)
git add nomeDoArquivoOuPasta (para adicionar na stagind area)
git commit -m "fraseExplicandoAAtualizacao" (para colocar no .git repository)

git config --global user.email "nomeDoEmail" (para criar quem esta executando a operacao)
git config --global user.name "nomeDaPessoa" (para criar quem esta executando a operacao)
git config -l (lista os dados de config do momento)
Só consegue commitar se tiver esses dados!!

git log (ve o que as acoes tomadas, os commit feitos e mesnagem) (ve os pontos na historia)
git log --name-status (da mais detalhes do log)
git diff (7 primeiros caracteres do log) => mostra as diferencas no arquivo comitado
git diff --staged => mostra os detalhes do que foi alterado no arquivo
git diff (7 carat log prim commit) (7caract 2 commit) => compara um commit com outro

git rm nomeDoArquivoDeletado => retira o arquivo deletado para preparar para o commit
git rm -r nomeDoDiretorioASerDeletado => remove um diretorio indesejado do git
pelo git diff e usando o log, é possivel recuperar os dados de um arquivo deletado

git add -f nomeDoArquivoOuDiretorio => força a adicao de um arquivo que esta no gitIgnore
git rm -r -f nomeDoDiretorio => forcaa remocao de um diretorio

git rm -rf nomeDoDiretorio/ --cached (retira o o diretorio da staging area, mas nao do diretorio de trabalho)

git add --all ou git add -A (faz as  adicoes de arquivos e delecoes, se houver...so o add nao remove arquivo deletado)

git config --global core.excludesfile ~/.gitIgnore => coloca globalmente um .gitIgnore por padrao

git commit -a -m "mensagem:..." => commita sem precisar passar pelo processo da adicao na staging area (cuidado pra nao querer ser muito rapido e fazer besteira)

se colocar so o git commit abre um editor de texto..melhor pra usar no github
git config --global -e (necessario modificar para "code --wait" o editor)
git config --global core.editor code (configurei o vscode, pra ver se da certo...deu certo)

git status (mostra o que esta sendo ou foi modificado apos o ultimo commit e o que está  sendo visto, mas nao esta no historico do git)

o git commit coloca nossos dados no git apos termos usado o git add . (esse modo pega tudo)

git diff (mostra as diferencas, o que foi modificado no documento)

digitar o 'Q' pra poder sair do log

git log --pretty=oneline => deixa mais bonito os log
git log --abbrev-commit => abrevia o log
git log --pretty=oneline --abbrev-commit => tudo junto
git log --stat => da estatiticas do log
git log -p => mostra a alteracao que foi feita no arquivo e por quem
git log -p -3 => mostra as ultimas 3 alteracoes

git branch => mostra a branch atual
git branch nomeDaBranch => cria uma ramificacao, normalmente feita para novas features, para nao danificar a versao anterior. O que e feito em uma branch nao afeta a outra...e criado uma referencia da anterior na nova branch, os logs sao os mesmos do anterior. Pode fazer um merge futuramente e mesclar a branch antiga e a nova

git checkout nomeDaBranch => entra na branch selecionada

o git por padrao nao salva diretorio vazio
ao entrar em um branch e outro,  percebe-se que diretorios aparecem e somem, pois cada branch tem sua historia

se estiver em outro branch e modificar um arquivo que esta na master, ele so permite fazer o checkout se commitar ou tirar do staging area. se olhar o arquivo na master, ele nao tem as atualizacoes do que tiver na branch, so quando fizer o merge

git merge nomeDoBranchASerAdicionadoAMaster => mescla o branch escolhido com a master

o ideal é criar uma branch dev e modificar la. so jogar pra master o tiver funcionando, versao final. A dev é beta.
vai criando novas branches para se trabalhar isolado...depois faz um merge de tudo na dev e se tiver tudo ok, pra master no final

o git é um reositorio local, so voce possui.
uma boa pratica na criacao do repositorio é que sua pasta repositorio tenha o mesmo nome do seu projeto, com o final .git nela (ex: /myproject.git)

para criar um diretorio que vai ser o repositorio, é so dentro do diretorio escolhido digitar:
git init --bare (claro que criar um repositorio na mesma maquina nao faz sentido, ela deve ficar em um servidor para que outros particpantes utilizem, é so pra estudar)

para sincronizar, quando tiver na pasta original, digitar:
git remote add origin caminhoParaAPastaRepositorio (C:/projetos/aulaGit.git/)

git remote -v => para visualizar
git push origin master => "empurre para o meu repositorio - myproject.git - o que tiver na minha maquina de origem, e coloque dentro da branche master

git push origin dev => dentro da branch dev, fazer isso pra jogar la no repositorio.git

simulando trabalho em grupo, onde tem um pasta servidor/ecomerce.git (dentro dela digito git init --bare)

...e na verissimo/ecomerce (onde irei trabalhar), dentro da pasta verissimo/ecomerce, digito git init
depois digito git remote add origin caminho do ecomerce.git
depois testa com git remote -v

para criar para vitor e artur, basta clonar
git clone C:/projetos/time/servidor/ecomerce.git/ (ele ja criar ate a pasta ecomerce). Apartir dai eles ja podem trabalhar juntos.

apos um arquivo ou trabalho ser concluido, dentro da sua pasta, add, commit e dar um git push origin master (dessa forma eu crio a branch master no servidor e o servider ja ve meu log e outras pessoas)

se Vitor for trabalhar no arquivo dele e tentar enviar seu arquivo, sem dar um "pull" no servidor, vai dar um erro.
git pull origin master (para ele poder receber meu arquivo index.html e atualizar qualquer arquivo que tiver)

sempre que for comecar a trabalhar em equipe, fazer primeiro o pull pra atualizar

no controle de versao centralizado, sempre que alguem tiver mexendo em um arquivo, nao sera possivel outra pessoa editar. O de versao distribuido é  descentralizado, varias pessoas podem acessar os mesmos arquivos, dando mais velocidade na programacao. Sempre fazer um pull quando for comecar a trabalhar,  senao pode dar conflito.

Usar   uma branch por feature.
para evitar varios commits por besteira, pode  usar o:
 git commit -m "kcdkjks" --amend (usar so se nao tiver dado push pro servidor, senao da conflito...se tiver so na sua mamquina, pode fazer)

 git merge --abort => aborta o commit feito antes
 pode analisar o que aconteceu, com git diff

 verificar como  funciona o meld e se o vscode  consegue fazer o mesmo

 git checkout nomeDoArquivoQueDesistiuDeModificar => retorna ao status anterior do arquivo
 git diff -w => nao mostra alteracoes com espaco, so problema de texto

 apos git log --oneline:
 git checkout 7primDigitosDoCommit => votla no tempo, podendo corrigir erros da epoca do log
 o git recomenda criar uma nova branch para manipular esses arquivos: git checkout -b voltandoNoTempo

 git checkout master => volta ao tempo normal de novo

o ideal é   o commit ter pouco codigo, organizado e claro, pra poder seencnotrar com mais facilidade
git checkout nomeDaBranchQueQuerIr -b subBranchCriada => cria uma sub branch estando em outra branch que nao é a que a da subbranch
ex: git checkout 1234567 -b voltaParaReparo

git stash => deixa pra depois em determinado arquivo, sem perder os dados. salva o working directory
git stash list => lista
git stash apply => volta para o working directory salvo
git stash drop stash@{numero} => deleta o stash
git stash pop

git show bb9c76d96b554aa950937aaac34e6c5f0bc18c50 (esta sequencia é um ponto salvo) => mostra o que foi modificado neste ponto

git show => mostra o ultimo ponto commitado
git branch nomeDoBranch=> cria uma nova ramificacao sem alterar o  que tinha antes (pode mudar que nao estraga o anterior...util para novas funcionalidades, antes de levar para a producao)
git checkout novaFuncionalidade => sai do ramo master e vai para o ramo da novaFuncionalidade

git checkout master => volta para o ramo principal
git branch => mostra todos os ramos

git add nomeDoArquivo => adiciona um arquivo especifico

git merge nomeDoBranch => adiciona os arquivos do branch ao principal
git branch -D novaFuncionalidade => deleta o branch selecionado

git remote add origin https://github.com/DaVinciDevBr/aulaGIT.git  (apos ter entrado no git hub e ter criado o repositorio, fazemos isso no terminal para adicionarmos nossos dados na nuvem do git hub)

git remote -v (mostra os repositorios remotos)

git branch -M main
git push -u origin master (empurra o repositorio local para o repositorio online. Na primeira vez precisa fazer isso, das vezes que atualizar, acho que so precisa do git push mesmo)

