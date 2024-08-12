# Comandos GitHub


## Comandos iniciais:
### git add . -> adicionar na stage
### git commit -m "Alterações" -> Salva no repositório local
### git push -> sobe para o github
### git status -> verifica o status
### git pull -> atualiza o repositório local
### git log -> acessa o histórico dos commits

## Respostas das demais perguntas:
### 10-) O que significa o git pull?

O comando git pull é utilizado para atualizar a sua branch local com as mudanças feitas no repositório remoto. Ele combina duas ações: git fetch e git merge. Aqui está uma explicação detalhada do que cada uma dessas ações faz e como elas se combinam no git pull:

### 1. git fetch
Quando você executa git fetch, o Git baixa os commits, arquivos e referências de uma branch remota para o seu repositório local. No entanto, isso não altera o estado da sua branch atual. Em vez disso, ele atualiza os ponteiros de branch remota (como origin/main) no seu repositório local.

###  2. git merge
Após o git fetch, o git pull automaticamente executa um git merge para mesclar as mudanças baixadas na sua branch atual. Se houver mudanças na branch remota que não estão presentes na sua branch local, essas mudanças serão aplicadas à sua branch local.

### Como git pull funciona
Quando você executa git pull, ele realiza as seguintes etapas:

#### Fetch:
Baixa todas as referências e objetos do repositório remoto.
#### Merge: 
Mescla as mudanças da branch remota (por exemplo, origin/main) na sua branch local.

### 11-) Acesse o histórico da sua branch atual (main):
git log -> 
O comando básico git log exibe uma lista de commits no histórico do repositório, começando pelo mais recente.

### A saída do git log inclui informações como:

- O hash do commit (um identificador único para cada commit);
- O autor do commit;
- A data do commit;
- A mensagem do commit.

### 12-) Crie uma tag do seu projeto:

Tags são usadas para marcar pontos específicos no histórico do seu repositório, geralmente para indicar lançamentos de versões. Existem dois tipos principais de tags no Git: anotadas e leves.

#### 1. Tag Leve
Uma tag leve é simplesmente um marcador para um commit específico. É como um ponteiro para um commit e não tem metadados adicionais como data, autor ou mensagem. Para criar uma tag leve:
git tag < nome-da-tag >

Por exemplo:
git tag Laura

#### Criar uma tag anotada:
git tag -a <nome-da-tag> -m "Mensagem sobre a tag"

#### Listar tags:
git tag

#### Mostrar informações sobre uma tag:
git show <nome-da-tag>

#### Enviar uma tag para o repositório remoto:
git push origin <nome-da-tag>

#### Enviar todas as tags para o repositório remoto:
git push --tags

#### Excluir uma tag localmente:
git tag -d <nome-da-tag>

#### Excluir uma tag no repositório remoto:
git push --delete origin <nome-da-tag>


### 13-) Inclua um título no index.html (ou outra modificação), crie uma branch com o nome feature/inclusão-do-título.

#### Criar e troque para a nova branch:
git checkout -b feature/inclusão-do-título

#### Modificar o index.html:
<title>Meu Novo Título</title>

#### Adicionar e faça commit das alterações:
git add index.html
git commit -m "Adiciona título ao index.html"


### 14-) Como acessar uma branch?
git branch - Listar todas as branches para verificar em qual você está

git checkout <nome-da-branch> - Trocar  acessar uma branch específica e trocar para esta.

#### Exemplo: git checkout feature/inclusão-do-título

### 15-) Como trocar de branch?
git checkout <nome-da-branch> - Trocar de branch

### 16-) Como deletar uma branch?
git branch -d <nome-da-branch> - Deletar uma branch
git branch -D <nome-da-branch> - Forçar a exclusão, caso a branch não tenha sido mesclada.
git push origin --delete <nome-da-branch> - deletar branch remota

### 17-) Entre na main branch e faça um merge da branch desejada para integrar ao main.
git checkout main - Trocar para a branch "main"
git merge feature/inclusão-do-título - Fazer o merge da branch desejada

### 18-) Para resolver o conflito do código, por que é preferível utilizar o rebase em vez do merge?

Rebase e merge são ambos usados para integrar mudanças de uma branch para outra, mas têm diferenças:

#### Rebase:
Reaplica commits da branch atual em cima da branch de destino, criando um histórico linear. Isso é útil para manter um histórico mais limpo e organizado.

git checkout feature/inclusão-do-título
git rebase main

Após o rebase, você pode precisar resolver conflitos e fazer um commit.

#### Merge: 
Cria um commit de merge que une as duas branches, preservando o histórico. Isso pode resultar em um histórico mais complicado, com commits de merge.

### 19-) Como inserir apenas um commit de uma branch para a main?
git checkout main - Trocar a branch para "main"
git log feature/inclusão-do-título - Encontrar o hash do commit
git cherry-pick <hash-do-commit> - Aplicar o commit específico

### 20-) Resete seu código até algum momento utilizando como parâmetro o hash da commit:
git reset --hard <hash-do-commit> - Para resetar seu código a um commit específico, utilizando o hash do commit.


### 21-) Crie um arquivo tipo txt e guarde em sua stash:
echo "Algum conteúdo" > meu-arquivo.txt - Criar arquivo "txt"
git add meu-arquivo.txt - Adicionar o arquivo no índice
git add meu-arquivo.txt - Guardar as alterações no stash


### 22-) Como fazer um Pull-Request?
git push origin feature/inclusão-do-título - Empurrar as mudanças para o repositório remoto.

#### Em sequência:
Vá para o GitHub e acesse o repositório.

Clique em "Compare & pull request".

Preencha os detalhes do Pull Request e clique em "Create pull request".

### 22-) Como adicionar Reviewers em seu repositório:

Para adicionar revisores a um Pull Request no GitHub:

Vá para o Pull Request no GitHub.

No lado direito, encontre a seção "Reviewers".

Clique no ícone de lápis ou na caixa de seleção e adicione os usuários que você deseja como revisores.

Clique em "Save" ou "Add".

![](img/00696483-d3b4-40b2-86a3-1685b29e8dec.jpg)
