# cursoGit
Curso Git Alura

git blame --> Mostra linha a linha quem mexeu no arquivo

git ls-files --> Mostra os arquivos que está gerenciando

git commit -a -m "Mensagem" --> Adiciona os arquivos que eram gerenciados pelo git, os arquivos novos não, e faz o commit.


git whatchanged --> Mostra os arquivos que foram alteradose
git whatchanged -p --> Mostra o que foi alterado nos arquivos em cada commit
git branch nomeDaBranch --> Cria a branch 

git push -u origin nomeDaBranch --> força a branch local ser igual a remota(ele sabe que as duas estão ligadas)

git branch -t nomeDaBranch origin/nomeDaBranch --> Baixa criando uma branch local "trackeada" com a original

git push -d origin nomeDaBranch --> Deletar uma branch

git fetch origin --> verifica todas as atualizações que ocorreram na branch

##### Rebase ####
1. git pull --> Atualiza a branch1(normalmente a master)
2. git rebase branch1 branch2 --> Joga os commits da branch1 na branch2, você deve estar na branch1 e ela depois fará o checkout na branch 2
3. git checkout branch1 --> vá para a branch1 via checkout
4. git merge branch2 --> faça o merdge com a branch2
5. git rebase --continue --> depois de resolver o conflito
#########


git checkout nomeArquivo --> Volta arquivo para ultimo estado(quando não está na staged area)
git reset nomeArquivo --> Retira o arquivo da staged area

git reset idDoCommit --> Volta para o commit(e deixa as alterações dele a ponto de adicionar na staged area e commitar) pelo que entendi

git revert idDoCommit --> Desfaz um commit sem perder os posteriores, gera outro commit pra isso.

git stash --> Guarda as alterações que não foram commitadas
git stash list --> Lista o que está guardado no stash
git stash apply numeroDoStash--> Retorna só o stash solicitado
git stash pop -> Retorna só o stash inteiro
git stash drop -> Dropa o stash 

##### bisect --> procura ####
git bisect start --> inicia bisect
git bisect bad HEAD --> Diz que o commit HEAD tem a alteração
git bisect god idCommit --> Diz que o commit idCommit não tem a alteração
git bisect bad --> Diz que o commit listado tem a alteração
git bisect good --> Diz que o commit listado não tem a alteração
git bisect bad --> Diz que o commit listado tem a alteração
git bisect good --> Se for o ultimo ele para, pegue o IDcommit e reverta, usar como base pra debugar o sistema
#########

git config --global credential.helper 'cache --timeout=21600' --> Adiciona timeout para digitar usuário e senha uma vez e durante a "sessão não precisar mais"

HEAD -->  referencia ao ultimo commit
HEAD~1 -->  referencia ao penultimo commit
HEAD~2 -->  referencia ao antepenultimo commit


git log --pretty=oneline --> mostra um commit por linha
git log --graph --> mostra os commits de forma grafica

git log -p --> Mostra os arquivos que foram alterados e e o diff

git diff e nomeDaBranch --> Mostra diferenças entre branchs

##### cherry-pick ####
git cherry-pick idDoCommit --> Traz só o commit solicitado
##Se der conflito resolva o conflito e 
git add arqquivosDoConflito
git commit -m "mensagem"

##### ####

git cherry-pick -n idDoCommit --> Traz as mudanças do commit, mas não o commit as alterações ficam na index

git cherry-pick commit10..commit25 --> Traz os commits solicitados ente o commit10 até o commit25 