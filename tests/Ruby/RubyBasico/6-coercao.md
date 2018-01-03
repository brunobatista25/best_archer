Coerção ou cast

Serve para transformar uma variável para inteiro,float ou string

```ruby
to_i - Converte a variável interiro
to_f - Converte a variável float
to_s - Converte a variável para string
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
