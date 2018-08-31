# Git & Github

## File Status Lifecycle
* Untracked -> criado mas ainda não visto pelo git.
* Unmodified -> depois que é adicionado no git.
* Modified -> se você editar.
* Staged -> arquivo na área onde vai ser criada a versão.
    * Quando é feito o commit, esses arquivos Staged voltam a ser Unmodified (nada foi modificado desde a última versão criada).

## Comandos
* git status -> vê o status dos arquivos
* git diff -> vê a diferença entre as versões
* git reset HEAD <file> -> tira o arquivo da fila do Stage.
* git checkout <file> -> remove toda a mudança, antes do commit.
* Para voltar a versão:
    * git reset --soft --mixed --hard
        * --soft -> Desfaz as modificações mas deixa o arquivo no Staged pronto pra fazer o commit de novo.
        * --mixed -> Desfaz as modificações e retorna o arquivo pra Modified (tira do Staged)
        * --hard -> desfaz as modificações e ignora tudo o que foi feito nele.