# Instalando o SitePrism

# Instalar

```ruby
gem install site_prism
```

# No arquivo Gemfile

```ruby
source 'http://rubygems.org'

gem 'capybara', '<3.3'
gem 'cucumber'
gem 'selenium-webdriver', '~>3.4'
gem 'rspec'
gem 'site_prism', '2.15.1'
```

# Usando SitePrism com Cucumber

```ruby
require 'capybara'
require 'capybara/cucumber'
require 'selenium-webdriver'
require 'site_prism'
```

# Usando SitePrism com Rspec

```ruby
require 'capybara'
require 'capybara/rspec'
require 'selenium-webdriver'
require 'site_prism'
```

# Criando um Page Objects


O Modelo de Objeto de Página é um padrão de automação de teste que visa criar uma abstração da interface de usuário do seu site que pode ser usada em testes. A maneira mais comum de fazer isso é modelar cada página como uma classe e, em seguida, usar instâncias dessas classes em seus testes.

Se uma classe representa uma página, então cada elemento da página é representado por um método que, quando chamado, retorna uma referência àquele elemento que pode ser acionado (clicado, definido como valor de texto) ou consultado (está habilitado? / visível?).

O SitePrism é baseado nesse conceito, mas vai além, como você verá abaixo, também permitindo a modelagem de seções repetidas que aparecem em várias páginas, ou muitas vezes em uma página usando o conceito de seções.

E para utilizar os métodos do SitePrism basta herdar da classe SitePrism::Page

```ruby
class Home < SitePrism::Page
  # corpo da classe
end
```

**Vamos para o próximo post** [Setando Url](https://github.com/brunobatista25/best_archer/blob/master/tests/SitePrism/03-setando_urls.md);