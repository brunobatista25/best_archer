
gem list

lista todas as gems instaladas no seu computador


gem list <nome da gem>

lista todas as gems instaladas com esse nome


gem list <nome da gem> --remote

busca la no site da ruby gem se procura se tem alguma gem com esse nome

gem list <nome da gem> --remote --all

busca la no site da ruby gem se procura se tem alguma gem com esse nome e traz todas as versoes

gem install faker

instalando a faker


gem install faker -v 1.0.0

instalando a faker com uma versao anterios


gem uninstall <gem>

desinstala uma gem

gem uninstall <gem> --version 1.0.0 ou -v 1.0.0

desinstala uma versao gem

gem cleanup -d 

mostra qual gems podem ser desisntaladas do sistema por serem antigas

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

# se quiserem usar uma determinada versão 

# gem faker '1.0.0'
# gem faker '>=1.0.0' instala uma versão maior ou igual a 1.0.0
# gem faker '~>1.0.0' pode variar a instalação mas nao passa de 1.1.1
# gem faker '~>1.6' pode variar a instalação mas nao passa de 2.0

#1.0.0
#major.minor.path

#quando a uma mudança muito grande no projeto.
#1 = major

#quando a alguma nova funcionalidade ou classe método etc..
#0 = minor

#path e para melhorias do software
#0 = path