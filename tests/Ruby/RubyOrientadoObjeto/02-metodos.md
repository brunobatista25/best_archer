# Método

def é uma palavra chave do Ruby para a definição (criação) de métodos, que podem, claro, receber parâmetros:

```ruby
def pessoa.vai(lugar)
  puts "indo para " + lugar
end
```
Mas, e o retorno de um método? Como funciona? Para diminuir o excesso de código que as linguagens costumam introduzir (chamado de ruído sintático), o Ruby optou por retornar o resultado da execução da última instrução executada no método. O exemplo a seguir mostra um método que devolve uma String:

```ruby
def pessoa.vai(lugar)
  "indo para " + lugar
end
```

Para visualizar esse retorno funcionando, podemos acessar o método e imprimir o retorno do mesmo:

```ruby
puts pessoa.vai("casa")
```

Podemos ainda refatorar o nosso método para usar interpolação:

```ruby
def pessoa.vai(lugar)
  "indo para #{lugar}"
end
```

Para receber vários argumentos em um método, basta separá-los por vírgula:

```ruby
def pessoa.troca(roupa, lugar)
  "trocando de #{roupa} no #{lugar}"
end
```

A invocação desses métodos é feita da maneira tradicional:

```ruby
pessoa.troca('camiseta', 'banheiro')
```

Alguns podem até ter um valor padrão, fazendo com que sejam opcionais:

```ruby
def pessoa.troca(roupa, lugar='banheiro')
  "trocando de #{roupa} no #{lugar}"
end
```

# invocação sem o parametro:

```ruby
pessoa.troca("camiseta")
```

# invocação com o parametro:

```ruby
pessoa.troca("camiseta", "sala")
```