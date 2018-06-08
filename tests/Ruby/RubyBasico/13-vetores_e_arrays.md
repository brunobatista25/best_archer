#Vetores e Arrays

## Vetor (array uni-dimensional)
É uma variável que armazena várias variáveis do mesmo tipo. No problema apresentado anteriormente, nós podemos utilizar um vetor de 50 posições para armazenar os nomes dos 50 alunos.

## Matriz (array multi-dimensional)
É um vetor de vetores. No nosso problema, imagine uma matriz para armazenar as 4 notas de cada um dos 50 alunos. Ou seja, um vetor de 50 posições, e em cada posição do vetor, há outro vetor com 4 posições. Isso é uma matriz.

Cada item do vetor (ou matriz) é acessado por um número chamado de índice.

No ruby usamos os bracket(conchetes).

```
[]
```

Exemplosde iniciar um array:

```
v = Array.new
v1 = []
puts v1
v2 = [1,2,3,4,5]
puts v2
v3 = [1,2,3,4,5]
puts v3[0]
v4 = Array.new(5,'a') # estou dizendo que quero 5 variaveis a nas 5 posições do array
puts v4
v5 = %w(Rio de janeiro) # pra cada espaco ele cria uma outra posicao no array
puts v5
```

atribuindo no array

```
v6 = [1,2,3,4,5]
v6 << [6]
puts v6
```
O vetor sempre começa na posição 0, ou seja o valor 1 está na posição 0 do array

```
[
 1,  #posição 0
 2,  #posição 1
 3,  #posição 2
 4,  #posição 3
 5   #posição 4
]
```