# Comandos gem

```ruby
gem list
```

Lista todas as gems instaladas no seu computador.

```ruby
gem list <nome da gem>
```

Lista todas as gems instaladas com esse nome.

```ruby
gem list <nome da gem> --remote
```

Busca la no site da ruby gem se procura se tem alguma gem com esse nome.

```ruby
gem list <nome da gem> --remote --all
```

Busca la no site da ruby gem se procura se tem alguma gem com esse nome e traz todas as versões.

```ruby
gem install faker
```

Instalando a faker

```ruby
gem install faker -v 1.0.0
```

Instalando a faker com uma versão anteriores

```ruby
gem uninstall <gem>
```

Desinstala uma gem

```ruby
gem uninstall <gem> --version 1.0.0 ou -v 1.0.0
```

Desinstala uma versão gem

```ruby
gem cleanup -d 
```

Mostra qual gems podem ser desinstaladas do sistema por serem antigas

```ruby
# Aqui estou dizendo a fonte de onde vou pegar a gems.
source 'https://rubygems.org'

# Lista das gems que eu irei usar
gem 'allure-rspec'
gem 'capybara'
gem 'chromedriver-helper'
gem 'faker'
gem 'rake'
gem 'rspec'
gem 'rubocop'
gem 'selenium-webdriver'
gem 'site_prism'
```

# Se quiserem usar uma determinada versão 

```ruby
gem faker '1.0.0'
```

Instala uma versão maior ou igual a 1.0.0

```ruby
gem faker '>=1.0.0' 
```

Pode variar a instalação mas nao passa de 1.1.1
```ruby
# gem faker '~>1.0.0' 
```

Pode variar a instalação mas nao passa de 2.0.

```ruby
# gem faker '~>1.6' 
```

# Falando sobre atualizações das gems
 
1.0.0
major.minor.path

Quando a uma mudança muito grande no projeto.
1 = major

Quando a alguma nova funcionalidade ou classe método etc..
0 = minor

Path e para melhorias do software
0 = path