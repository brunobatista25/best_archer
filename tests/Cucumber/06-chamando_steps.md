# Calling Steps from Step Definitions(Chamando Passos das Definições de Etapas)

É possível chamar etapas de Definições de Etapas :

```ruby
# ruby 
Dado / ^ o usuário (. *) existe $ / do | name | 
  # ... 
end 

Dado / ^ eu logo como (. *) $ / do | name | 
  # ... 
end 

Quando /^(.*) está logado em $ / do | name | 
  passo "o usuário # {nome} existe" 
  etapa "eu logar como # {nome}" 
fim
```

A partir da versão 0.4.4 você também pode fazer isso:

```ruby
Dado /^(.*) está logado em $ / do | name | 
  # Look ma, sem citações! 
  # Mais fácil de fazer "extrair passos de texto simples" refatorações com corte e colar! 
  step% Q { 
    Dado o usuário # {nome} existir 
    Dado eu logar como # {nome} 
  } 
end
```

Invocar etapas de definições de etapas é prático se você tiver várias etapas comuns que deseja executar em vários cenários. - Simplesmente se você quiser tornar seus cenários mais curtos e mais declarativos. Isso permite que você faça isso em um Cenário:

```
# recurso 
Cenário: Veja os últimos incidentes 
  Dado que Linda está logada # Isso, de fato, invocará definições de 2 passos 
  Quando eu for para a página do incidente
```

Em vez de ter muita repetição:

```
# feature 
Cenário: Veja os últimos incidentes 
  Dado o usuário Linda existe 
  E eu logo como Linda 
  Quando eu vou para a página do incidente
```

## Calling steps with multiline step arguments(Chamando etapas com argumentos de várias etapas)

Às vezes, você quer chamar um passo que foi projetado para levar os argumentos da etapa Multiline , por exemplo:

## Tables(Tabelas)

```ruby
# ruby 
Dado / ^ um relatório de despesas para (. *) com as seguintes posts: $ / do | date, posts_table | 
  # A variável posts_table é uma instância de Cucumber :: Ast :: Table 
end
```

Isso pode ser facilmente chamado a partir de um passo de texto simples como este:

```
# feature 
Dado um relatório de despesas para janeiro de 2009 com as seguintes postagens: 
  | conta | descrição | quantidade | 
  | INT-100 | Táxi | 114 | 
  | CUC-101 | Peeler | 22 |
```

Mas e se você quiser chamar isso de uma definição de passo? Há algumas maneiras de fazer isso:

```ruby
# ruby 
Dado / Um simples relatório de despesas / 
  step "um relatório de despesas para janeiro de 2009 com as seguintes postagens:", table (% { 
    | conta | descrição | montante 
    | INT-100 | Taxi | 114 
    | CUC-101 | Peeler | 22 | 
  }) 
end
```

Ou, se você preferir uma abordagem mais programática:

```ruby
# ruby 
Given / Um simples relatório de despesas / 
  step "um relatório de despesas para janeiro de 2009 com as seguintes postagens:", table ([ 
    % w {quantidade da descrição da conta}, 
    % w {INT-100 Taxi 114}, 
    % w {CUC -101 Peeler 22} 
  ]) 
fim
```

Você também pode simplesmente receber uma mesa e passá-la para baixo. Esta definição de passo em espanhol passa sua tabela para o inglês:

```ruby
# ruby 
Então / ^ debo ver los links: $ / do | links_table | 
  Então "Eu deveria ver os links:", link_table 
end 

Então / ^ Eu deveria ver os links: $ / do | links_table | 
  links_table.hashes.each do | hash | 
    Então "Eu deveria ver o link # {hash ['link']}" 
  end 
end
```

## Multiline Strings(Cordas Multilíneas)

Para chamar um passo que leva uma string de várias linhas, como

```ruby
# ruby 
Dado / ^ Eu preencho "([^ \"] *) "com $ / do | campo, pystring | 
  fill_in (campo:: com => pystring) 
end
```

a partir de uma definição de passo, passe a string após a etapa:

```ruby
# ruby 
Dado / ^ existe um documento com conteúdo $ / do | pystring | 
  step 'Eu vou adicionar um documento'
  step 'Eu preencho" ditacontent "com ', pystring 
  step ' Eu pressiono" Add to repository "' 
end
```

Vamos para o próximo post [Esquema do Cenário](https://github.com/brunobatista25/best_archer/blob/master/tests/Cucumber/07-esquema_cenario.md); 

## Referências:
	
https://github.com/cucumber/cucumber