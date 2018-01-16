# Mas primeiro vamos falar o que é a integração contínua?

A integração contínua é uma prática de desenvolvimento de software de DevOps em que os desenvolvedores, com frequência, juntam suas alterações de código em um repositório central. Depois disso, criações e testes são executados. Geralmente, a integração contínua se refere ao estágio de criação ou integração do processo de lançamento de software, além de originar um componente de automação (ex.: uma CI ou serviço de criação) e um componente cultural (ex.: aprender a integrar com frequência).

# E qual principal objetivo da integração contínua?

Os principais objetivos da integração contínua são encontrar e investigar bugs mais rapidamente, melhorar a qualidade do software e reduzir o tempo que leva para validar e lançar novas atualizações de software.

# O que é Codeship?

O Codeship é um serviço de entrega contínua hospedado que se concentra na velocidade, confiabilidade e simplicidade. Você configura o Codeship para criar e implantar seu aplicativo do GitHub para o cenário ou a plataforma de produção de sua escolha.

O serviço oferece uma variedade de poderosas opções de configuração. Atualmente, o Codeship é integrado aos populares gestores de código fonte GitHub e Bitbucket. Ele suporta uma variedade de linguagens de programação (Ruby on Rails, Node.js , PHP, Java, Go, Dart, etc.) e plataformas de implantação (Amazon Web Services, Heroku, Google App Engine, etc.)

A prática de integração contínua envolve repetidos testes automatizados e fusão de código com notificações para alertar os desenvolvedores para problemas em seu código em tempo real. O Codeship combina isso com a prática de entrega contínua , que prevê a implantação regular de códigos uma vez que as mudanças passaram testes automatizados.


# Então vamos configurar nosso Codeship?

# 1- Passo

Crie uma conta no codeship é de graça:

https://app.codeship.com/registrations/new?utm_source=NavBar

# 2- Passo

Escolha qual o repositório que você usa, no meu caso eu uso github, então irei usá-lo nos exemplos, mas o conceito é a mesma coisa para os outros repositórios.

# 3- Passo

Nesta tela você irá colocar o link do seu projeto, mesma coisa como se você fosse clonar o seu projeto. Basta copiar o link do seu pojeto e colar na página do codeship.

# 4- Passo

Nessa nossa aula iremos usa a versão básica

# 5- Passo

Vamos escolher qual linguagem usaremos no codeship,nesse post usaremos a linguagem Ruby

Depois de escolher a linguagem o codeship já irá criar uns comandos básicos.

O codeship já vem com vários pacotes já instalados nele por padrão,se precisar saber quais são basta acessar esse link abaixo:

https://documentation.codeship.com/basic/builds-and-configuration/packages/

Os comandos de configuração que usaremos pra rodar os testes automatizados são:

```
rvm use 2.4.2 — install
export CHROMEDRIVER_VERSION=2.33
rvm use $(cat .ruby-version) –install
```

Estamos instalando a versão 2.4.2 do RVM

```
rvm use 2.4.2 — install
```

Dando um update no chromedriver e setando a versão a ser usada.

(OBS: O Codeship já vem de padrão instalado o chromedriver 2.31)

```
export CHROMEDRIVER_VERSION=2.33
```

Setando a versão do ruby

```
rvm use $(cat .ruby-version) –install
```

# 6- Passo

Depois de ter configurando o ambiente agora iremos configurar os comandos para executar os testes no segundo terminal abaixo.

```
cd src
bundle install
bundle exec cucumber
```

Estou entrando dentro da pasta onde está o meu arquivo gemfile

```
cd src
```
Instalando as dependencias que eu selecionei no meu gemfile

```
bundle install
```

Executando o comando para rodar o meu projeto

```
bundle exec cucumber
```

Depois basta salvar que o codeship irá rodar automaticamente os seus testes.

A clicar em cima do projeto vocês veram um dashboard como este abaixo.

Ao finalizar os testes terá 3 tipos de situações :

Success — Este é o melhor caso onde todos os testes passaram.

Error — Quando alguma coisa do codeship deu erro ou falhou.

Failed — Quando seus testes falharam.

# Referências:

https://medium.com/@brunobatista101/aprenda-a-fazer-integra%C3%A7%C3%A3o-cont%C3%ADnua-dos-seus-testes-automatizados-com-capybara-codeship-6463f4e2209e

https://codeship.com/	