O comando gets serve para ler coisas  que são inseridas no teclado

O comando puts imprime o resultado na tela

```ruby
puts "ola"
puts "Digite seu nome:"
v1 = gets.chomp
puts "O seu nome é " + v1
```

O comando \n - insere uma nova linha ou enter
O comando chomp retira a quebra de linha

```
gets.chomp
```

O comando inspect verifica o que tem dentro da variável que pode estar escondida

```ruby
puts "Digite a sua idade?"
v2 = gets.chomp
puts "Sua idade é " + v2.inspect
puts "Sua idade é " + v2
```