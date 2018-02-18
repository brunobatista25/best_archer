# Classe

Uma classe é um gabarito para a definição de objetos. Através da definição de uma classe, descreve-se que propriedades -- ou atributos -- o objeto terá.

Além da especificação de atributos, a definição de uma classe descreve também qual o comportamento de objetos da classe, ou seja, que funcionalidades podem ser aplicadas a objetos da classe. Essas funcionalidades são descritas através de métodos. Um método nada mais é que o equivalente a um procedimento ou função, com a restrição que ele manipula apenas suas variáveis locais e os atributos que foram definidos para a classe.

A especificação de uma classe é composta por três regiões:

# Nome da classe
Um identificador para a classe, que permite referenciá-la posteriormente -- por exemplo, no momento da criação de um objeto.

# Atributos

O conjunto de propriedades da classe. Para cada propriedade, especifica-se:

nome: um identificador para o atributo.
tipo: o tipo do atributo (inteiro, real, caráter, etc.)
valor_default: opcionalmente, pode-se especificar um valor inicial para o atributo.
visibilidade: opcionalmente, pode-se especificar o quão acessível é um atributo de um objeto a partir de outros objetos. Valores possíveis são:

(privativo), nenhuma visibilidade externa;

(público), visibilidade externa total;
 
(protegido), visibilidade externa limitada.

# Métodos

O conjunto de funcionalidades da classe. Para cada método, especifica-se sua assinatura, composta por:

nome: um identificador para o método.

tipo: quando o método tem um valor de retorno, o tipo desse valor.

lista de argumentos: quando o método recebe parâmetros para sua execução, o tipo e um identificador para cada parâmetro.
visibilidade: como para atributos, define o quão visível é um método a partir de objetos de outros classes.

As técnicas de programação orientada a objetos recomendam que a estrutura de um objeto e a implementação de seus métodos devem ser tão privativos como possível. Normalmente, os atributos de um objeto não devem ser visíveis externamente. Da mesma forma, de um método deve ser suficiente conhecer apenas sua especificação, sem necessidade de saber detalhes de como a funcionalidade que ele executa é implementada.

# Criando uma classe

O nome da classe sempre começa com letra maiúscula 

```ruby
class NomeDaClasse
    #CORPO DA CLASSE
end 
```

# Como instância uma classe

```ruby
objto1 = NomeDaClasse.new
```