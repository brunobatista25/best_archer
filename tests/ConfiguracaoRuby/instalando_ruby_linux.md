Como instalar Ruby no Ubuntu com Rbenv

O rbenv fornece suporte para trabalhar versões específicas do aplicativo do Ruby, permite alterar o Ruby global para cada usuário e permite usar uma variável de ambiente para substituir a versão do Ruby.

Pré-requisitos
Este tutorial irá levá-lo através do processo de instalação do Ruby via rbenv. Para seguir este tutorial, você precisa ter um servidor Ubuntu 14.xx ou 16.xx e o usuário comum (não root).

Update do Ubuntu e Dev Dependencies

```ruby
$ sudo apt-get update
$ sudo apt-get install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm3 libgdbm-dev
$ sudo apt-get install git
```

Instalar Rbenv
Com os seguintes comandos:

```ruby
$ git clone https://github.com/rbenv/rbenv.git ~/.rbenv
$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
$ echo 'eval "$(rbenv init -)"' >> ~/.bashrc
$ source ~/.bashrc
$ type rbenv
```

Se deu tudo certo, você deve ver a seguinte saída:

```ruby
Output
rbenv is a function
rbenv () 
{ 
    local command;
    command="$1";
    if [ "$#" -gt 0 ]; then
        shift;
    fi;
    case "$command" in 
        rehash | shell)
            eval "$(rbenv "sh-$command" "$@")"
        ;;
        *)
            command rbenv "$command" "$@"
        ;;
    esac
}
```

Instalar Ruby Build

```ruby
$ git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```

Instalando o Ruby
Este comando, deve carregar em cache a lista de versões disponíveis para instalação:

```ruby
$ rbenv install -l
```

Agora instale a versão desejada (eu escolhe a versão 2.4.1)

```ruby
$ rbenv install 2.4.1
```

Com o comando abaixo, você define a versão global do Ruby no sistema

```ruby
$ rbenv global 2.4.1
```

Para verificar se deu tudo certo, digite o comando:

```ruby
$ ruby -v
```

Deverá aparece algo como:

```ruby
ruby 2.4.1
```

REFERÊNCIAS:

https://medium.com/@papito/como-instalar-ruby-com-rbenv-no-ubuntu-a75d1999362b
