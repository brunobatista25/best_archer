# Estrutura de Repetição


For -- O laço for é uma estrutura de repetição muito utilizada, É muito útil quando se sabe de antemão quantas vezes a repetição deverá ser executada.

While -- Enquanto o teste for verdadeiro vai fazer o bloco de repetição.

Until -- enquanto for falso não vai fazer nada.

Loop -- Um loopirá executar qualquer código dentro do bloco (mais uma vez, isso é apenas entre o {}ou do ... end) até que intervir manualmente com Ctrl + cou inserir uma breakdeclaração dentro do bloco, que irá forçar o loop para parar e a execução continuará após o loop.

```
a = 0
for i in 0..10 do
a = a + 1
end

puts a
```

```
i = 1

while i <= 50
    puts "bruno - #{i}"
    i += 1
end
```

```
#aqui o 1 está com o valor de 50 
# i == 50
until i <= 1
    puts "sou falso - #{i}"
    i -= 1
end
```

```
loop do
   a = gets.chomp
   if a = sair do
     exit
   end
end
```
