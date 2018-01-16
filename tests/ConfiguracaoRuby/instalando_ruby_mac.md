# Instalando Ruby on Mac

# Instalando Homebrew
Primeiro, precisamos instalar o Homebrew . O Homebrew nos permite instalar e compilar pacotes de software para MacOS.

O Homebrew vem com um script de instalação muito simples. Quando solicitar que você instale o XCode CommandLine Tools, diga sim.

Agora abra o Terminal e execute o seguinte comando:

```ruby
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

# Instalando Ruby
Agora que temos o Homebrew instalado, podemos usá-lo para instalar o Ruby. Nós vamos usar o rbenv para instalar e gerenciar nossas versões do Ruby.

Para fazer isso, execute os seguintes comandos em seu Terminal:

```ruby
brew install rbenv ruby-build
echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
source ~/.bash_profile
# Instalando Ruby 2.4.3
rbenv install 2.4.3
rbenv global 2.4.3
ruby -v
gem install bundler
```

# Instalando Rails
Instalar Rails é muito simples. Executa o seguinte comando:

```ruby
gem install rails -v 5.1.4
```

Agora precisamos liberar acesso ao executável do Rails, para isso bastar rodar o seguinte comando:

```ruby
rbenv rehash
```

Para verificar se deu tudo certo:

```ruby
rails -v
# Rails 5.1.4
```

# REFERÊNCIAS:

https://medium.com/@papito/instalando-o-ruby-no-macos-435f451b86a8