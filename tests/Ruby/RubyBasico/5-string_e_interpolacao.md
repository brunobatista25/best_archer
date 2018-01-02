String é tudo aquilo que está dentro de um "" ou ''

exemplo

```ruby
puts "string"
puts 'string'
```

```ruby
v1 = 'Bruno'
puts "Hello!" + v1

v2 = "Bruno"
```

Para concatenar apenas e feita por uma variavel que estaja dentro de aspas duplas.

Para contatenar uma variável e preciso que ela esteja neste formato:

Começando com hastag e chaves,e dentro da chaves a variável.

#{variavel}

Exemplo de interpolação

```ruby
este codigo não consegue interpolar devido ter apenas aspas simples.
puts 'Beleza? #{v2}'


puts "Beleza? #{v2}"

puts "A soma de 1 + 2 é: #{1 + 2}"
```