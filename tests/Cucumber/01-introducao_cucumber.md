# Introdução ao Cucumber

Cucumber é uma ferramenta que suporta o Desenvolvimento Guiado por Comporamento (BDD - Behavior-driven Development).
O Cucumber faz a leitura das especificações em texto e valida se o que o software está executando está de acordo com a especificação. A especificação consiste em diversos cenários ou exemplos.
Cada cenário é uma lista de passos para o Cucumber trabalhar em cima. O Cucumber consegue verificar se o Software está entregando o negócio conforme a especificação e reporta com ✅ se o cenário passou ou com ❌ se o cenário quebrou.

## Introdução ao BDD.

O BDD foi concebido por Dan North, a partir de uma insatisfação com a falta de informações dos testes de TDD (“Test driven development”). Dan queria saber mais sobre o que deveria ser testado e como esse teste deveria ser realizado. A ideia principal do BDD é possibilitar que as funcionalidades do sistema sejam escritas em linguagem natural.

O BDD é uma abordagem que serve para integrar os testes com as regras de negócios e também com a linguagem de programação focando no comportamento do software usando uma [linguagem ubíqua](https://pt.linkedin.com/pulse/domain-driven-design-linguagem-ub%C3%ADqua-veranildo-veras) (Ubiquitous Language). Assim melhorando a comunicação com as equipes.

O BDD usa várias linguagens mas nesse tutorial iremos dar foco em uma linguagem chamada Gherkin. 

O Gherkin é uma linguagem que foi criada para descrições de comportamento.  Ela tem a capacidade de remover detalhes da lógica de programação e focar no comportamento que uma funcionalidade deve ter. Ela suporta várias linguagens. Veja abaixo um exemplo de uma funcionalidade na linguagem gherkin.

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
#language: pt-br <é usado par que a linguagem gherkin identifique o idioma português >

Funcionalidade <é onde faz a descrição da funcionalidade>

Como um <usuário/ator>

Eu quero <meta a ser alcançada>

De modo que <a razão para alcançar a meta>

Cenário: <onde e feita a descrição do teste>

Dado <um estado conhecido>

Quando<um determinado evento ocorre>

Então <isso deve ocorrer>
```

A linguagem Gherkin é independente de qualquer linguagem de programação. Pode ser utilizada para criar testes/software em java ,ruby , python etc. Basta colocar um .feature no nome do arquivo.

```ruby
Ex: fazerLogin.feature
```

## Vantagens

- Maior entendimento do requisito proposto.
- Menos tempo investido em escrita de casos de testes.
- Mais tempo investido em análise de cobertura de testes.
- Estes testes podem ser utilizados por desenvolvedores na automatização.
- Fácil manutenção de templates.


### **Próximo post:** [Instalação do Cucumber](https://github.com/brunobatista25/best_archer/blob/master/tests/Cucumber/02-instalacao_cucumber.md);


## Referências:
	
https://github.com/cucumber/cucumber
https://medium.com/@brunobatista101/da-s%C3%A9rie-1-aprenda-cucumber-com-batista-1b75ba2fb0a5
