# Instalando o SitePrism

# Instalar

```ruby
gem install site_prism
```

# No arquivo Gemfile

```ruby
source 'http://rubygems.org'

gem 'capybara', '3.0.3'
gem 'cucumber'
gem 'selenium-webdriver'
gem 'rspec'
gem 'site_prism', '2.15'
gem 'faker'
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

E para utilizar os métodos do SitePrism basta herdar da classe SitePrism::Page

```ruby
class Home < SitePrism::Page
  # corpo da classe
end
```

**Vamos para o próximo post** [Setando Url](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/03-setando_urls.md);