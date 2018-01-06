# Git

Nesta sessão serão apresentados alguns dos principais comandos Git no desenvolvimento e manutenção de software. Primeiramente será necessário baixar o git no seu computador, abaixo seguem os instaladores e seus respectivos sistemas operacionais:

* [Instalador Windows](https://git-scm.com/download/win);
* [Instalador Linux/Unix](https://git-scm.com/download/linux);
* [Instalador MAC OS X](https://git-scm.com/download/mac);

---
## Configurando a sua Identidade Git

O primeiro passo na configuração do Git é definir suas credenciais de acesso aos repositórios, isso é importante ao enviar e baixar as modificações em seu código. O comando básico para isto é este:

```
$ git config --global user.name "Eduardo Pacheco"
$ git config --global user.email eduardo.pacheco@aprendendogit.com.br
```
Lembrando que podemos utilizar o comando acima sem o parâmetro '--global' para projetos específicos, este é um parâmetro apenas pra facilitar o acesso aos projetos de um só repositório.

**_Obs.: Existem algumas outras configurações como a escolha do editor de texto padrão, ferramenta para a solução de conflitos, entre outras que podem ser visualizadas através deste link: [Configurações iniciais Git](https://git-scm.com/book/pt-br/v1/Primeiros-passos-Configura%C3%A7%C3%A3o-Inicial-do-Git)_**

Após a instalação do Git podemos começar a utilizar a ferramenta de duas formas básicas. Estas são criar um novo repositório a partir de algum projeto local ou baixar algum repositório remoto já pré-existente. Os comandos para estes dois casos são o seguinte:

---
## Iniciando com o Git

O primeiro comando apresentado neste tutorial será o para criar um repositório a partir de um projeto local, para isto vá até o diretório onde o projeto esta e execute o seguinte comando:

```
git init
```
Assim como podemos criar um repositório a partir de um projeto local, podemos também baixar uma cópia de um repositório remoto a partir deste comando:
```
git clone /caminho/do/repositório
```
O comando para realizar o clone de um servidor remoto utilizando credenciais de acesso a este servidor se dá através deste comando:
```
git clone username@ip_do_servidor:/path/to/repo.git
```
---
## Entendendo o Fluxo de Trabalho do Git

O fluxo de trabalho do Git se resume a três etapas, sendo elas (Apresentas da direita pra esquerda na imagem abaixo):

1. **Working Directory/Work Tree:** _Onde esta armazenado a cópia do repositório no seu computador e onde haverão as modificações para ser enviado ao repositório remoto posteriormente;_
2. **Index/Stage:** _Onde estarão os arquivos temporários, passíveis de serem enviados ou não para o servidor remoto;_
2. **HEAD:** _Onde esta a versão final dos códigos que serão enviados para o servidor remoto._

![alt text](https://backlog.com/git-tutorial/en/img/post/intro/capture_intro1_4_1.png)

### 1. Adicionando arquivos ao diretório remoto

Após realizarmos a configuração do Git e fazermos o clone de um repositório na qual queremos realizar alterações, o próximo passo é enviar as modificações realizadas para o resto do time, para isto existem alguns passos, o primeiro é verificar os arquivos modificados através do comando:

```
git status
```
O retorno no console deverá ser algo parecido com isto:

```shell
> git status
On branch comandos_github
Your branch is up-to-date with 'origin/github'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:  github.md

no changes added to commit (use "git add" and/or "git commit -a")
```
No exemplo acima temos um arquivo para ser enviado ao servidor remoto. O próximo passo é inserir o(os) arquivos ao **Index**, o comando será esse:

```
git add <nome_do_arquivo>
```
Ou caso queiramos enviar todos os arquivos de uma só vez basta inserir um ponto após a tag 'add':
```
git add .
```

Para confirmar que queremos que estas modificações sejam enviadas para o servidor remoto, temos que 'commitar', ou seja confirmar o envio para o servidor remoto:

```
git commit -m "Criando tutorial Git"
```
**_Obs.: O parâmetro '-m' é obrigatório e significa a mensagem do commit, ou seja, uma breve descrição sobre o que você acabou de alterar no código_**

Pronto! Já está tudo no servidor remoto então e todos podem utilizar o meu código então? ÉÉÉÉÉÉ..Ainda não :sweat_smile:

Precisamos enviar as modificações para o servidor remoto com o comando **push**:

```
git push origin master
```

Sendo que podemos também alterar a branch\* na qual iremos enviar as modificações. No exemplo acima enviamos as modificações direto para a branch principal (master) mas poderíamos enviar para a branch **github** por exemplo:

```
git push origin github
```

### Mas o que são Branches?!

Diferente de outros controladores de versão, o Git tem como diferencial criar 'Cópias de Repositórios' para dentro de sua máquina. Ou seja, criamos a cópia de um repositório estável e em cima dela desenvolvemos as features para posteriormente serem inseridas nesta versão estável do repositório.

![alt text](https://grapefruitgames.files.wordpress.com/2013/05/unitygitdiagram.png)

Normalmente a branch principal de um projeto é a branch **master**. Não é uma prática aceitável realizar **commits** e dar **push** diretamente nesta branch. Por isso o recomendável é criar branches locais e após isso realizar a inserção do que foi desenvolvido na **master**.

Para saber a branch na qual estamos trabalhando o comando é este:
```
git branch
```
Este comando retornará as branches que temos localmente e marcará com um asterisco qual é a branch atual.

Podemos mudar a branch quando bem entendermos através do comando **checkout**:

```
git checkout nome_da_branch
```
