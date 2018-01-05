Hashes

Hashes (dicionários)

Hashes (também conhecidos como arrays associativos, mapas ou dicionários) são similares aos arrays a medida que são coleções indexadas de referências a objetos. No entanto, enquanto o o array é indexado por inteiros (semelhante a um índice remissivo), o hash pode ser indexado com objetos de qualquer tipo: strings, expressões regulares e assim por diante. Quando você armazena um valor em um hash, você na verdade fornece dois objetos – o índice (normalmente chamado de chave) e o valor desse índice. É possível recuperar os valores utilizando o índice do hash. Os valores do hash, assim como os índices, podem ser objetos de qualquer tipo.

O exemplo  abaixo cria um hash com literais (strings): uma lista de pares chave => valor entre

```ruby
ruby codigo_exemplo.rb
h = {'cachorro' => 'canino', 'gato' => 'felino',
    'burro' => 'asinino', 12 => 'dodezino'}
puts h.length  # 4
puts h['cachorro']  # 'canino'
puts h
puts h[12]
```

A saída do código acima é:

```ruby
 >ruby codigo_exemplo.rb
 4
 canino
 {"cachorro"=>"canino", "gato"=>"felino",
  "burro"=>"asinino", 12=>"dodezino"}
 dodezino
 >Exit code: 0
 ```

Caso o programa apresentado no exemplo seja executado no Ruby 1.8 a saída será um pouco diferente. Em todos exemplos estamos utilizando o Ruby 1.9, no qual o hash é apresentado de forma ordenada e igual a sua declaração. Já no Ruby 1.8 a ordenação do hash é diferente da declarada

Comparados com arrays, os hashes têm uma vantagem significativa: eles podem usar qualquer objeto como índice.

Hashes têm um valor padrão. Tal valor é retornado após uma tentativa de acesso a uma chave não existente. Por padrão este valor é nil.

A classe Hash tem muitos métodos e você pode consultá-los aqui (em inglês).

Usando Símbolos como chaves do Hash
Ao invés, de utilizar uma string como chave, de preferência pelo uso de um símbolo. Veja o exemplo a seguir no programa codigo_exemplo.rb.

```ruby
1 # codigo_exemplo.rb
2 pessoa = Hash.new
3 pessoa[:apelido] = 'GuruIndiano'
4 pessoa[:idioma] = 'Marata'
5 pessoa[:sobrenome] = 'Talim'
6 puts pessoa[:sobrenome] # Talim
```

Outro exemplo p0411symbolhash.rb.

```ruby
1 # codigo_exemplo.rb
2 h = {:apelido => 'GuruIndiano', :idioma => 'Marata', :sobrenome => 'Talim'}
3 puts h
```

A saída do exemplo acima é:

```ruby
1 {:apelido=>"GuruIndiano", :idioma=>"Marata", :sobrenome=>"Talim"}
```

Outra maneira de fazer a mesma coisa é mostrada no programa p0412symbolhash.rb.

```ruby
1 # codigo_exemplo.rb
2 h = {apelido: 'GuruIndiano', idioma: 'Marata', sobrenome: 'Talim'}
3 puts h
```

A saída é:

```ruby
1 {:apelido=>"GuruIndiano", :idioma=>"Marata", :sobrenome=>"Talim"}
```

Ou seja, exatamente o mesmo que ocorreu na execução do programa codigo_exemplo.rb.

REFERÊNCIAS:

https://guru-sp.github.io/tutorial_ruby/hashes-ruby.html