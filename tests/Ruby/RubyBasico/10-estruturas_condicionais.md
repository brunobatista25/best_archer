Estruturas condicionais

if elsif else:

IF(se) a condição for atendida faça algo, ELSIF (senão, se) outra condição for atendida faça algo, ELSE (senão) faça algo, END (fim da condição).

Unless:

O controle unless é como a estrutura if, só que negativa, ao contrário do if, basicamente o uso é o mesmo do if só que ao contrário, apenas isso. 

Case when

Avalia uma lista de condições e retorna uma das várias expressões de resultado possíveis, a expressão CASE tem dois formatos: CASE simples compara uma expressão com um conjunto de expressões simples para determinar o resultado e a expressão CASE que avalia um conjunto de expressões booleanas para determinar o resultado. Ambos os formatos suportam um argumento ELSE opcional.

```ruby
puts "Digite um número"
v1 = gets.chomp.to_i

#se a variavel v1 for maior que 10
if v1 > 10 
#entao imprime
    puts "O valor digitado é maior do que 10"
#se nao    
else
    puts "O valor digitado é menor ou igual 10"
end

if v1 > 10 then#então
    puts "O valor digitado é maior do que 10"
else
    puts "O valor digitado é menor ou igual 10"
end
```

```ruby
puts "Digite um número"
v1 = gets.chomp.to_i

if v1 > 10 then#então
    puts "O valor digitado é maior do que 10"
elsif v1 >= 5
    puts "O valor digitado é maior ou igual que 5(entre 5 e 10)"
else
    puts "O valor digitado é menor 5"
end
```



E o inverso do if ele faz a negação
Exemplo: 
A menos que v1 seja menor que 10

```ruby
puts "Digite um número"
v1 = gets.chomp.to_i

#A menos que v1 seja menor que 10
unless v1 > 10
    puts "O valor é menor que 10"
else 
    puts "O valor e maior que 10"
end
```

```ruby
puts "Digite um número de 1 a 5"
v1 = gets.chomp.to_i

case v1
when 1
    puts "Você escolheu o número 1"
when 2
    puts "Você escolheu o número 2"
when 3
    puts "Você escolheu o número 3"
when 4
    puts "Você escolheu o número 4"
when 5
    puts "Você escolheu o número 5"
else
    puts "Opção Inválida!"
end
```
