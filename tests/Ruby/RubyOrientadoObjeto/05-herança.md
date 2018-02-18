# O que é Herança ?

A Herança é um dos pilares da programação orientada a objetos e é uma técnica comumente utilizada quando se quer reaproveitar código já existente e também descrever uma relação entre classes de modo que determinadas classes possam herdar atributos e métodos de uma classe de nível superior.

Essas classes podem ser descritas como: Classe Pai, Superclasse ou Classe Base, que é a classe que contém as características que serão herdadas pelas classes de nível mais baixo na hierarquia.

E existem também as descritas: Classes Filhas, Derivadas ou Subclasses, que são justamente as classes que herdam as características de sua classe base e também podem conter suas próprias característas, ou ainda refinar (especializar para o seu contexto) uma determinada característica herdada de sua classe base.

A Herança descreve uma relação é do tipo entre as classes que estão nessa hierarquia. Conforme o exemplo abaixo:

```ruby
class Calendar
  attr_reader :start_date, :end_date

  def initialize; end

  def date_range
    raise 'Must implement!'
  end
end

class WeeklyCalendar < Calendar
  def date_range
    base_date.beginning_of_week(:sunday)..base_date.end_of_week(:sunday)
  end
end

class MonthlyCalendar < Calendar
  def date_range
    base_date.beginning_of_month.beginning_of_week(:sunday)..base_date.end_of_month.end_of_week(:sunday)
  end
end
```

Na hierarquia proposta acima é possível verificar a superclasse Calendar e analisar que as classes WeeklyCalendar e MonthlyCalendar possuem uma relação é do tipo com relação a superclasse Calendar, afinal de contas essas classes representam um tipo de calendário, porém mais especializadas.

Dessa forma o uso da Herança pode ser aplicado como técnica para descrever a relação entre as classes e também aplicar o reuso de código. Importante notar também que apesar de utilizar a Herança para reaproveitar determinados trechos de código, cada tipo de calendário também pode especializar as características que forem necessárias para seu contexto, no caso do exemplo cada calendário implementa seu próprio método date_range.

Quais os principais problemas com uso de Herança ?
Se a Herança faz tudo isso que foi dito acima, por quais motivos ela pode ser ruim para o desenvolvimento ?

Um dos principais problemas encontrados ao fazer uso massivo de Herança é o alto acoplamento e o baixo encapsulamento de informações de cada classe.

Quanto maior o acoplamento mais difícil é alterar as classes, realizar modificações em uma classe base sem que essa modificação se propague para suas classes filhas, ou em casos mais graves, um erro escrito em uma classe irá se propagar para as demais dentro da hierarquia. E o baixo encapsulamento se da ao fato que as classes envolvidas podem acabar tendo muito conhecimento do estado interno de outras classes.

Outro problema relacionado ao auto acoplamento criado pela Herança é que torna difícil que comportamentos sejam adicionados ou removidos em tempo de execução, ou então fazer objetos terem outros comportamentos para diferentes contextos em diferentes momentos dentro do software.

Nem sempre uma subclasse precisa herdar todos os atributos ou métodos de sua superclasse, nesse caso há uma quebra do Princípio de Segregação de Interface, que dita que classes não devem implementar aquilo que não irão utilizar apenas para satisfazer a Herança.

Por fim, a Herança pode parecer uma boa alternativa em primeiro momento porém com o passar do tempo e o crescimento do software as classes começam a crescer e ganhar diferentes comportamentos, ficando cada vez mais diferentes até chegar a um ponto que a relação entre as classes antes ditas como é do tipo X estarem mais com cara de compartilham algumas funcionalidades com Y, desse modo não fazendo mais sentido o uso de Herança.

REFERÊNCIAS:

http://shipit.resultadosdigitais.com.br/blog/composicao-e-heranca-no-ruby/