# Configuração

Depois de ter instalado os [Drivers](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/02-instalando_drivers.md)

Agora vamos configurar nosso projeto ruby com capybara

Primeiro vc precisa ter instalado o [Bundler](https://github.com/brunobatista25/best_archer/blob/master/tests/Bundler/01-introducao_bundler.md)


Agora crie um arquivo  chamado Gemfile sem nenhuma extensão, agora dentro do arquivo coloque os seguintes conteúdos:

```
source 'http://rubygems.org'

gem 'capybara'
gem 'chromedriver-helper'
gem 'selenium-webdriver'
```

Essa são as gems minímas para se configurar o projeto com capybara

Capybara será o framework de desenvolvimento.

Selenium Webdriver será o Driver base e abrir o Chrome para automação.

Agora rode o comando

```
bundle install
```

Todas a gems serão instaladas e um outro arquivo sera criado automaticamente Gemfile.lok

## Configurando o ENV.RB

Dentro desse arquivo temos que especificar as gems que serão utilizadas

```
require 'capybara'
require 'selenium-webdriver'
```

## Agora iremos adicionar umas configurações do capybara neste mesmo arquivo:

```ruby
require 'capybara'
require 'selenium-webdriver'

Capybara.configure do |config|
  config.default_driver = :selenium
  config.app_host = "https://www.google.com/"
  config.default_max_wait_time = 30
end
```

```ruby
#Estou definindo que o driver que vou utilizar e o selenium webdriver.
Capybara.default_driver = :selenium 
```

```ruby
#Esse comando e a configuraçaão para qual tempo minímo para esperar um elemento na tela
Capybara.default_max_wait_time = 30 
```

```ruby
#Aqui configuro qual url so site que estou usando
Capybara.app_host
```

## Configurar qual navegador  usar para automação

Dentro deste mesmo arquivo iremos colocar a configuração de qual navegador iremos usar

## Chrome

OBS: para usar o chrome e preciso dar instalar a seguinte gem:

```ruby
gem 'chromedriver-helper'
```

Para usar o chrome basta usar o seguinte comando

```ruby
Capybara.register_driver :selenium do |app|
  Capybara::Selenium::Driver.new(app, :browser => :chrome)
end
```

## Firefox

Para usar o firefox basta usar o seguinte comando

```ruby
Capybara.register_driver :selenium do |app|
  Capybara::Selenium::Driver.new(app, :browser => :firefox)
end
```

 O arquivo env.rb ficará desse jeito:

 # Chrome

```ruby
  require 'capybara'
  require 'selenium-webdriver'
  
  Capybara.register_driver :selenium do |app|
    Capybara::Selenium::Driver.new(app, :browser => :chrome)
  end
  
  Capybara.configure do |config|
    config.default_driver = :selenium
    config.app_host = "https://www.google.com/"
    config.default_max_wait_time = 30
  end
```

 #Firefox

```ruby
  require 'capybara'
  require 'selenium-webdriver'
  
  Capybara.register_driver :selenium do |app|
    Capybara::Selenium::Driver.new(app, :browser => :firefox)
  end
  
  Capybara.configure do |config|
    config.default_driver = :selenium
    config.app_host = "https://www.google.com/"
    config.default_max_wait_time = 30
  end
```

## Referências:

https://github.com/teamcapybara/capybara

https://github.com/thiagomarquessp/capybaraforall/