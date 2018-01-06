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

```
:heavy_exclamation_mark: Existem algumas outras configurações como a escolha do editor de texto padrão, sua ferramenta para a solução de conflitos default, entr outras que podem ser visualizadas através deste link: [Configurações iniciais Git](https://git-scm.com/book/pt-br/v1/Primeiros-passos-Configura%C3%A7%C3%A3o-Inicial-do-Git)
```

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
