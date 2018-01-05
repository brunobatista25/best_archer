Símbolo

Um símbolo (Symbol) se parece com um nome de variável mas é prefixado com dois pontos (:). Exemplos: :action, :line_items. Você não precisa pré-declarar um símbolo e garante-se que eles sejam únicos. Não há necessidade de se atribuir algum tipo de valor para um símbolo – Ruby cuida disso para você. A linguagem também garante que não importa onde apareça em seu programa, um símbolo particular terá sempre o mesmo valor.

Alternativamente, você pode considerar que os dois pontos significam “coisa chamada”. Assim, :id é “a coisa chamada id”. Você pode pensar também em :id significando o nome da variável id, e o id (sem os dois pontos) significando o valor da variável.

Um símbolo é o objeto Ruby mais básico que você pode criar. Ele é apenas um nome e um ID interno. Símbolos são úteis porque um dado nome de símbolo se refere ao mesmo objeto através de um programa Ruby. Símbolos são mais eficientes que strings. Duas strings com o mesmo conteúdo são dois objetos diferentes, mas para qualquer nome existe apenas um objeto Symbol. Isso pode economizar tempo e memória.

Veja o exemplo exemplo.rb abaixo:

```ruby
1 # exemplo.rb
2 # use o object_id da classe Object
3 # ele retorna um inteiro identificador para um objeto
4 puts "string".object_id
5 puts "string".object_id
6 puts :symbol.object_id
7 puts :symbol.object_id
```

A saída quando rodei o programa no meu PC foi:

```ruby
1 >ruby exemplo.rb
2 21066960
3 21066930
4 132178
5 132178
6 >Exit code: 0
```

Então, quando usamos uma string e quando usamos um símbolo?

Se o conteúdo (a sequência de caracteres) do objeto é importante, use uma string.
Se a identidade do objeto é importante, use um símbolo.

Ruby usa símbolos e mantem uma tabela de símbolos para armazená-los. Símbolos são nomes – nome de variáveis de instância, nomes de métodos, nomes de classes. Então, se existe um método chamado control_movie, existe automaticamente um símbolo :control_movie. Ruby é interpretado, então ele mantem sua tabela de símbolos acessível o tempo todo. Você pode encontrar o que está nela a qualquer momento chamando Symbol.all_symbols.

Um objeto do tipo símbolo é criado prefixando-se um operador, string, variável, constante, método, classe ou módulo como dois pontos. O objeto símbolo será único para cada diferente nome mas não se referirá particularmente a instância do nome, durante a execução do programa. Então, se Fred é uma constante em um contexto, um método em outro e uma classe em um terceiro, o símbolo :Fred será o mesmo objeto em todos os três contextos.

Isso pode ser ilustrado por esse simples programa – exemplo.rb:

```ruby
 1 # exemplo.rb
 2 class Test
 3   puts :Test.object_id.to_s
 4   def test
 5     puts :test.object_id.to_s
 6     @test = 10
 7     puts :test.object_id.to_s
 8   end
 9 end
10 t = Test.new
11 t.test
```

A saída que obtive quando rodei o programa no meu PC foi:

```ruby
1 >ruby p039xsymbol.rb
2 116458
3 79218
4 79218
5 >Exit code: 0
```

Aqui temos outro exemplo – exemplo.rb:

```ruby
1 # p039xysymbol.rb
2 sabe_ruby = :sim
3 if sabe_ruby == :sim
4   puts 'Voce eh um rubista'
5 else
6   puts 'Aprenda Ruby'
7 end
```

A saída é:

```ruby
1 >ruby p039xysymbol.rb
2 Voce eh um rubista
3 >Exit code: 0
```

No exemplo, :sim é um símbolo. Símbolos não contêm valores ou objetos como as variáveis Ao invés disso, eles são usados como um nome consistente no código. Por exemplo, no código mostrado anteriormente você poderia facilmente substituir o símbolo por
uma string como no exemplo exemplo.rb:

```ruby
1 # exemplo.rb
2 sabe_ruby = 'sim'
3 if sabe_ruby == 'sim'
4   puts 'Voce eh um rubista'
5 else
6   puts 'Aprenda Ruby'
7 end
```

Isto tem o mesmo resultado, mas não é mais eficiente. Nesse exemplo, cada menção do ‘sim’ cria um novo objeto armazenado separadamente em memória, enquanto símbolos são valores com referência única inicializados apenas uma vez. No primeiro exemplo,
apenas :sim existe, enquanto no segundo exemplo você têm duas strings ‘sim’ e ‘sim’ ocupando espaço na memória.

Podemos também transformar uma string em um símbolo e vice-versa:

```ruby
1 puts "string".to_sym.class # Symbol
2 puts :symbol.to_s.class    # String
```

Símbolos são particularmente úteis quando se cria hashes e você quer distinguir chaves e valores. Veja o tópico usando símbolos como chaves hash para exemplos práticos.

REFERÊNCIAS:

https://guru-sp.github.io/tutorial_ruby/simbolos.html