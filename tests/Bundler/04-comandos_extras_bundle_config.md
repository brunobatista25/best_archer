# Opção do bundle config

As opções que podem ser configuradas são:

```ruby
bin
```

Cria um diretório (padrão para ~/bin) e coloca todos os executáveis ​​a partir da gema lá. Esses executáveis ​​são executados no contexto do Bundler. Se usado, você pode adicionar este diretório à PATHvariável do seu ambiente . Por exemplo, se a railsgema vem com um railsexecutável, esta bandeira criará um bin/railsexecutável que garanta que todas as dependências referidas serão resolvidas usando as gemas agrupadas.

```ruby
deployment
```

No modo de implantação, o Bundler irá "lançar" o pacote para productionuso. Verifique com atenção se você deseja que esta opção seja ativada developmentou testambientes.

```ruby
path
```
A localização para instalar as gemas especificadas. Este padrão é a configuração do Rubygems. Bundler compartilha esta localização com Rubygems, gem install ...também terá gem instalado lá. Portanto, gemas instaladas sem uma --path ...configuração aparecerão ligando gem list. Consequentemente, as gemas instaladas em outros locais não serão listadas.

```ruby
without
```

Uma lista de grupos separados por espaços referentes a gemas para ignorar durante a instalação.

```ruby
with
```

Uma lista separada por espaço de grupos referentes a gemas para incluir durante a instalação.
