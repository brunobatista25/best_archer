# Inicializando objetos

No momento do nascimento

Vamos começar de novo e definir uma nova classe.

Lembre-se de como dissemos que os objetos podem ser pensados ​​como duas coisas: sabem coisas e podem fazer coisas .

Vamos definir uma aula Person. As pessoas, obviamente, também sabem coisas e podem fazer coisas.

Veja como definir uma classe brilhante, nova e vazia Person:

```ruby
class Person
end
```

Novamente, essa não é uma classe muito útil, mas podemos instanciá-la, e criar uma instância real, concreta pessoa (objeto) a partir dele:

```ruby
p Person.new
```

Agora, antes de adicionar qualquer comportamento (métodos) à nossa classe, queremos poder dar alguns dados iniciais: no nosso caso, queremos que a pessoa conheça seu próprio nome.

Nós podemos fazer isso assim:

```ruby
class Person
  def initialize(name)
  end
end
```

Você vê que nós adicionamos um método chamado initializepara a classe, e esse método aceita um único argumento, chamado name. No momento, esse método ainda está vazio. Vamos adicionar um pouco de código a ele um pouco.

O bit importante para aprender para você é: o método initializeé um método especial com um significado especial em Ruby:

Sempre que você chamar o método newem uma classe, como dentro Person.new, a classe criará uma nova instância de si mesma. Então, internamente, chamará o método initializeno novo objeto. Ao fazê-lo, simplesmente passará todos os argumentos que você passou new para o método initialize.

Então, podemos agora criar uma nova instância de pessoa chamando ...

```ruby
Person.new("Ada")
```

... e a string "Ada"será transmitida ao nosso initializemétodo e acabará sendo atribuída à variável local name.

O método especial initializeé chamado sob o capô quando o objeto foi criado pelo método de classe new.

Obviamente, nosso initializemétodo não faz nada com a String passada, ainda assim. Está certo. Chegaremos a isso no próximo capítulo.

Para recapitular, quando você invoca newa classe Persone passa a string "Ada", o método newcriará uma nova instância da classe e ligará initializepara ela, passando a mesma lista de argumentos, que em nosso caso é a única string "Ada".

Quando criamos uma nova instância de uma classe pela forma de chamar o método new nessa classe, também dizemos que "instanciamos" esse objeto: Ao chamar, Person.newcriamos um novo objeto de pessoa.
