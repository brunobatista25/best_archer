O Bundler fornece um ambiente consistente para projetos Ruby, rastreando e instalando gemas e versões exatas que são necessárias.

Bundler é uma saída do inferno de dependência e garante que as gemas que você precisa estão presentes no desenvolvimento, estadiamento e produção. Começar o trabalho em um projeto é tão simples quanto bundle install.

Começando

Começar com bundler é fácil! Abra uma janela do terminal e execute este comando:

```ruby
$ gem install bundler
```

Especifique suas dependências em um Gemfile na raiz do seu projeto:

```ruby
source 'https://rubygems.org'
gem 'nokogiri'
gem 'rack', '~> 2.0.1'
gem 'rspec'
```

Intalando as gems com bundle
Instale todas as gemas necessárias das suas fontes especificadas:

```ruby
$ bundle install
```
$ git add Gemfile Gemfile.lock


1. [Comandos Bundler](https://github.com/brunobatista25/best_archer/blob/master/tests/Bundler/comandos_bundler.md);