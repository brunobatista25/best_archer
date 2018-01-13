Introdução ao Cucumber

Irei falar de um do frameworks mais conhecidos quando o assunto e BDD(Behaviour-Driven-Development ou Desenvolvimento Guiado por Comportamento). Que vem sendo muito utilizado atualmente, principalmente pela galerinha que faz testes automatizados.

Batista o que é BDD?


Introdução ao BDD.

O BDD foi concebido por Dan North, a partir de uma insatisfação com a falta de informações dos testes de TDD (“Test driven development”). Dan queria saber mais sobre o que deveria ser testado e como esse teste deveria ser realizado. A ideia principal do BDD é possibilitar que as funcionalidades do sistema sejam escritas em linguagem natural.

O BDD é uma abordagem que serve para integrar os testes com as regras de negócios e também com a linguagem de programação focando no comportamento do software usando uma linguagem ubíqua (Ubiquitous Language). Assim melhorando a comunicação com as equipes.

Linguagem Ubíqua: é uma linguagem estruturada em torno do modelo de domínio e usada por todos os membros da equipe para conectar todas as suas atividades com o software. Numa equipe de desenvolvedores são: os jargões técnicos, terminologias das discussões do dia-a-dia ou uma linguagem incomum para pessoas de outros departamentos.

O BDD usa várias linguagens mas nesse post iremos da foco em uma linguagem chamada Gherkin é uma linguagem que foi criada para descrições de comportamento, ela tem a capacidade de remover detalhes da lógica de programação e focar no comportamento que uma funcionalidade deve ter. Ela suporta várias linguagens. Veja abaixo um exemplo de uma funcionalidade na linguagem gherkin.

Exemplo:

```ruby
#language: pt-br
Funcionalidade: Fazer Login

 Eu, como usário
 Desejo fazer login na aplicação

Cenário: Fazer login na aplicação
Dado que eu tenho um usuário e senha
Quando eu faço login
Então eu verifico se estou logado na aplicação
```


```ruby
#Language: pt-br <é usado par que a linguagem gherkin identifique o idioma português >

Funcionalidade <é onde faz a descrição da funcionalidade>

Como um <usuário/ator>

Eu quero <meta a ser alcançada>

De modo que <a razão para alcançar a meta>

Cenário: <onde e feita a descrição do teste>

Dado <um estado conhecido>

Quando<um determinado evento ocorre>

Então <isso deve ocorrer>
```

A linguagem Gherkin é independente da linguagem pode fazer em java ,ruby , python etc. Basta colocar um .feature no nome do arquivo.

```ruby
Ex: fazerLogin.feature
```

Vantagens

Maior entendimento do requisito proposto.
Menos tempo investido em escrita de casos de testes.
Mais tempo investido em análise de cobertura de testes.
Estes testes podem ser utilizados por desenvolvedores na automatização.
Fácil manutenção de templates.

Vamos para o próximo post [Instalação do Cucumber](https://github.com/brunobatista25/best_archer/blob/master/tests/Cucumber/02-instalacao_cucumber.md);

Referências:
	
https://github.com/cucumber/cucumber

https://medium.com/@brunobatista101/da-s%C3%A9rie-1-aprenda-cucumber-com-batista-1b75ba2fb0a5