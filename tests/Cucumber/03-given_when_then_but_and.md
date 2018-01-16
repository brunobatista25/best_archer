# Given(Dado) When(Quando) Then(Então) And(e) But(mas)

Depois de ter feito a [Instalação do Cucumber](https://github.com/brunobatista25/best_archer/blob/master/tests/Cucumber/02-instalacao_cucumber.md);

Agora vamos por em prática!

Vamos criar nosso primeiro arquivo feature.
Primeiro é preciso salvar o arquivo como ".feature".

```
login.feature
```

A linguagem gerkin ela pode ser escrita em vários idiomas,para os tutorias eu irei usar em pôrtugues mesmo pra o fácil aprendizado.

Para podermos dizer qual linguagem sera utilizada temos que colocar o seguinte comando na primeira linha do arquivo:

```
# language: pt
```

Segundo passo e dizer qual a funcionalidade que iremos testar:

```
# language: pt

Funcionalidade: Fazer Login

```

O cenarios do cucumber consistem em etapas, também conhecidas como Givens, Whens e Thens.

O cucumber não distingue tecnicamente entre esses três tipos de etapas. No entanto, recomendamos que você faça! Essas palavras foram cuidadosamente selecionadas para seu propósito, e você deve saber qual é o propósito de entrar na mentalidade do BDD .

Robert C. Martin escreveu uma ótima publicação sobre o conceito Given-When-Then do BDD, onde ele pensa neles como uma máquina de estados finitos.

# Given(Dado)

O objetivo dos dados é colocar o sistema em um estado conhecido antes que o usuário (ou sistema externo) comece a interagir com o sistema (nas etapas Quando). Evite falar sobre a interação do usuário em dados. Se você criasse casos de uso, os dados seriam suas condições prévias.

Exemplos:

Crie registros (instâncias do modelo) / configure o estado do banco de dados.
Está certo chamar a camada "dentro" da camada UI aqui (em Rails: converse com os modelos).
Faça login em um usuário (Uma exceção à recomendação sem interação. As coisas que "aconteceram anteriormente" estão ok).
E para todos os usuários Rails lá fora - recomendamos usar um dado com um argumento de tabela multilinha para configurar registros em vez de dispositivos elétricos. Desta forma, você pode ler o cenário e dar sentido a isso sem ter que procurar em outro lugar (nas luminárias).

# When(Quando)

O objetivo de As etapas é descrever a ação-chave que o usuário executa (ou, usando a metáfora de Robert C. Martin, a transição do estado).

Exemplos:

Interagir com uma página web (Webrat / Watir / Selenium interação etc deve principalmente ir para quando passos).
Interaja com algum outro elemento da interface do usuário.
Desenvolver uma biblioteca? Chutando algum tipo de ação que tenha um efeito observável em outro lugar.

# Then(Então)

O objetivo de Then steps é observar os resultados . As observações devem estar relacionadas ao valor / benefício da empresa na descrição do recurso. As observações também devem estar em algum tipo de saída - que é algo que vem de fora do sistema (relatório, interface de usuário, mensagens) e não algo que está profundamente enterrado dentro dela (que não tem valor comercial).

Exemplos:

Verifique se algo relacionado ao dado + Quando é (ou não) na saída
Verifique se algum sistema externo recebeu a mensagem esperada (um e-mail com conteúdo específico foi enviado?)
Embora possa ser tentador implementar, em seguida, etapas para apenas procurar no banco de dados - resista à tentação. Você só deve verificar o resultado que é observável para o usuário (ou sistema externo) e os bancos de dados geralmente não são.

# And,But(E,mas)

Se você tem vários dados, whens ou thens você pode escrever

```
Cenário : Múltiplos Givens 
  Dado um
   dado Dado outro
   dado Dado ainda outra coisa
   Quando eu abro meus olhos
   Então eu vejo algo
   Então eu não vejo outra coisa
```

Ou você pode fazê-lo ler mais fluentemente escrevendo

```
Cenário : Múltiplos Givens 
  Dado uma coisa
     E outra coisa
     E ainda outra coisa
   Quando eu abro meus olhos
   Então eu vejo algo
     Mas eu não vejo outra coisa
```

Para passos de cucumber começando com E ou Mas são exatamente o mesmo tipo de etapas que todos os outros.

Agora vamos continua com nossa feature que ficaria desse jeito


```
# language: pt

Funcionalidade: Fazer Login

Cenário: Fazer login com sucesso.
Dado que eu tenha um usuário.
Quando faço login.
Então eu verifico se o login foi realizado. 

```

Depois disso basta digitar o seguinte comando no terminal:

```
cucumber
``` 

O cucumber irá gerar os metódos em qual lnguagem você estiver usando, no nosso caso e ruby.

Então o resultado será esse:

```
# language: pt
Funcionalidade: Fazer Login

  Cenário: Fazer login com sucesso.              #features/step_definitions/login.feature:5
    Dado que eu tenha um usuário.                #features/step_definitions/login.feature:6
    Quando faço login.                           #features/step_definitions/login.feature:7
    Então eu verifico se o login foi realizado.  #features/step_definitions/login.feature:8
  
1 scenario (1 undefined)
3 steps (3 undefined)
0m0.147s

You can implement step definitions for undefined steps with these snippets:

Dado("que eu tenha um usuário.") do
  pending # Write code here that turns the phrase above into concrete actions
end

Quando("faço login.") do
  pending # Write code here that turns the phrase above into concrete actions
end

Então("eu verifico se o login foi realizado.") do
  pending # Write code here that turns the phrase above into concrete actions
end

```

Esse e o primeiro passo para se criar os steps onde o código abaixo será inserido em algum arquivo .rb e dentro dos metodos serem feito os comandos de automações.

```
Dado("que eu tenha um usuário.") do
  pending # Write code here that turns the phrase above into concrete actions
end

Quando("faço login.") do
  pending # Write code here that turns the phrase above into concrete actions
end

Então("eu verifico se o login foi realizado.") do
  pending # Write code here that turns the phrase above into concrete actions
end
```

Vamos para o próximo post [Background](https://github.com/brunobatista25/best_archer/blob/master/tests/Cucumber/04-background.md);

# Referências:
	
https://github.com/cucumber/cucumber
