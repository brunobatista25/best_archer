Interador each

Each Iterator: Eu gosto bastante do iterador each. É bem simples e expressivo. Para uma lista de valores, vamos iterar passando 1 por 1 dentro do bloco do iterador. Dentro dele podemos usar a variável definida.

```ruby
[1, 2, 3, 4, 5].each do |num|
  puts num
end
```

Você, talvez, esteja se perguntando o por que de usar o iterator each ao invés de usar for. A grande diferença é que o iterador each mantém a variável apenas dentro do seu escopo. Enquanto o for. mantém a variável viva fora do seu escopo. Vamos fazer um teste:

```ruby
# for vs each

# for looping
for num in 1...5
  puts num
end

puts num # => 5

# each iterator
[1, 2, 3, 4, 5].each do |num|
  puts num
end

puts num # => undefined local variable or method `n' for main:Object (NameError)
```

A variável num continuará “viva” após o bloco de iteração do loop for. Enquanto para o iterador each essa variável não existirá mais fora de seu escopo.

REFERÊNCIAS:

https://medium.com/trainingcenter/ruby-101-o-b%C3%A1sico-260e8605962