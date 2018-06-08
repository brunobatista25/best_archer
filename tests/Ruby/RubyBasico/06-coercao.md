Coerção ou cast

Serve para transformar uma variável para inteiro,float,string,simbolo ou array

```ruby
to_i #Converte a variável inteiro
to_f #Converte a variável float
to_s #Converte a variável para string
to_sym #Converte a variável para simbolo
to_a #Converte a variável para array
```

Exemplo:

```ruby
puts "Digite sua idade:"
v1 = gets.chomp
v2 = v1.to_i + 1
puts "Sua idade ano que vem será? #{v2}"

#tentando  interporlar sem converter
puts "Digite sua idade:"
v1 = gets.chomp.to_i
v2 = v1 + 1
puts "Sua idade ano que vem será? #{v2}"
```
