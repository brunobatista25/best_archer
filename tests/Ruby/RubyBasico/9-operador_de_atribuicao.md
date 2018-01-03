Operadores de atribuicao
Quando queremos atribuir um valor a mais na mesma variavel e usado desde jeito:

```ruby
a = a + 1
```
Pra isso temos varias formas de se resolver.

```ruby
 a = a + 4  atribui um valor a uma variavel
 a += 4 equivale  a = a + 4
 a -= 4 equivale  a = a - 4
 a *= 4 equivale  a = a * 4
 a %= 4 equivale  a = a % 4
 a /= 4 equivale  a = a / 4
 a **= 4 equivale  a = a ** 4
```

```ruby
a = 2
a += 4 # a = a + 4
puts a
```

```ruby
b = 4
b -= 2 # a = a - 2
puts b
```

```ruby
c = 4
c /= 2 # a = a / 2
puts c
```

```ruby
d = 4
d *= 4 # a = a * 4
puts c
```

```ruby
e = 2
e **= 4 # a = a ** 4
puts e
```

```ruby
f = 10
f %= 5 # a = a % 5
puts f
```
