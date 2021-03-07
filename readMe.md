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

git diff (7 carat log prim commit) (7caract 2 commit) => compara um commit com outro

git rm nomeDoArquivoDeletado => retira o arquivo deletado para preparar para o commit
pelo git diff e usando o log, é possivel recuperar os dados de um arquivo deletado

git add --all ou git add -A (faz as  adicoes de arquivos e delecoes, se houver...so o add nao remove arquivo deletado)


git status (mostra o que esta sendo ou foi modificado apos o ultimo commit e o que está  sendo visto, mas nao esta no historico do git)

o git commit coloca nossos dados no git apos termos usado o git add . (esse modo pega tudo)

git diff (mostra as diferencas, o que foi modificado no documento)

digitar o 'Q' pra poder sair do log

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

