# Scenario Outlines(Esquema do Cenário)

Copiar e colar cenários para usar diferentes valores rapidamente torna-se tedioso e repetitivo:

```
Cenário : coma 5 em 12 
  Dado que existem 12 pepinos
   Quando eu como 5 pepinos
   Então eu deveria ter 7 pepinos Cenário : comer 5 de 20 Dado que há 20 pepinos
   Quando eu comer 5 pepinos
   Então eu deveria ter 15 Pepinos
```

Os esquema do cenário nos permitem expressar de forma mais concisa esses exemplos através do uso de um modelo com espaços reservados, usando Esquema do Cenário, Exemplos com tabelas e < > parâmetros delimitados:

```
Esquema do Cenário: Comer 
  Dado que existem <início> pepinos
   Quando eu comer <comer> pepinos
   Então eu deveria ter <left> Pepinos 
   
   Exemplos :
     | Comece | coma | esquerda |
     |  12    |  5   |  7       | 
     |  20    |  5   |  15      |
```

As Esquema do cenário fornecem um modelo que nunca é executado diretamente. Um cenário de cenário é executado uma vez para cada linha na Exemplo seção abaixo dela (sem contar a primeira linha).

A maneira como isso funciona é através de espaços reservados. Os marcadores de posição devem estar contidos nos < > passos do cenário do cenário. 
Por exemplo:

```
Dado <eu sou um marcador de posição e estou bem>
```

Os espaços reservados indicam que, quando a linha Exemplos é executada, eles devem ser substituídos por valores reais da Exemplos tabela. Se um nome de espaço reservado for o mesmo que um título de coluna na Exemplos tabela, esse é o valor que o substituirá.

Você também pode usar marcadores de posição em argumentos de etapa multilinha.

IMPORTANTE: Suas definições de etapa nunca terão que corresponder a um espaço reservado. Eles precisarão combinar os valores que irão substituir o marcador de posição.

Então, ao executar a primeira linha do nosso exemplo:

```
Exemplos :
   | Comece | coma | esquerda | 
   |  12    |  5   |  7       |
```

O cenário que realmente é executado é:

```
Cenário Destaque : comer 
  Dado que há 12 pepinos       # <start> substituídos por 12 
  Quando eu como 5 pepinos             # <comer> substituído por 5 
  Então eu deveria ter 7 pepinos     # <à esquerda> substituídos por 7
  ```
  
## Referências:
	
https://github.com/cucumber/cucumber