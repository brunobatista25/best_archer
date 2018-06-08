# Operadores logicos

Os operadores lógicos são usados ​​para comparar duas expressões e retornar um resultado booleano (verdadeiro ou falso). Esses operadores juntam essas expressões retornando verdadeiro ou falso.

```ruby
&&  equivale   a  e
||  equilvale  a  ou
!   equivale   a  negacao
```

```ruby
Operador	O que faz?                                        	                 Exemplo	                Método?
and ou &&	#Se ambas condições forem verdadeiras, então é retornado true	     (a && b) é verdadeiro	    Não
or ou ||	#Se algumas das condições forem diferente de zero, o retorno é true 	(a or b) é verdadeiro	Não
not ou !	#Inverte o estado da lógica do operando	                            !(a && b) é falso	        Não
```

```ruby
v1 = 34
v2 = 56
v3 = 2 
v4 = 7
```

```ruby
if (v1 < v2) && (v3 < v4)
    puts "condicao atendida nos dois casos"
else
    puts "condicao não atendida nos dois casos"
end
```
# ou

```ruby
if (v1 < v2) and (v3 < v4)
    puts "condicao atendida nos dois casos"
else
    puts "condicao não atendida nos dois casos"
end
```

```ruby
# pelo uma condicao sendo atendida
if (v1 < v2) || (v3 > v4)
    puts "condicao atendida nos dois casos"
else
    puts "condicao não atendida nos dois casos"
end
```
#ou

```ruby
if (v1 < v2) or (v3 > v4)
    puts "condicao atendida pelo menos em um casos"
else
    puts "condicao não atendida nos dois casos"
end
```

```ruby
#esta negando os dois casos
if !(v3 < v4)
    puts "negacao atendida"
else
    puts "negacao nao atendida"
end
```

```ruby
#esta negando os dois casos
if !(v3 > v4)
    puts "negacao atendida"
else
    puts "negacao nao atendida"
end
```