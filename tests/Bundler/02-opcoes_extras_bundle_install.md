#Opções do bunlde install

Para aplicar qualquer um --binstubs, --deployment, --path, ou --withoutcada vez que bundle installé executado, usar bundle config(ver pacote-config (1) ).

```ruby
--binstubs[=<directory>]
```

Cria um diretório (padrão para ~/bin) e coloca todos os executáveis ​​a partir da gema lá. Esses executáveis ​​são executados no contexto do Bundler. Se usado, você pode adicionar este diretório à PATHvariável do seu ambiente . Por exemplo, se a railsgema vem com um railsexecutável, esta bandeira criará um bin/railsexecutável que garanta que todas as dependências referidas serão resolvidas usando as gemas agrupadas.

```ruby
--clean
```

Ao finalizar a instalação, o Bundler irá remover todas as gemas que não estejam presentes no Gemfile atual (5) . Não se preocupe, gemas atualmente em uso não serão removidas.

```ruby
--deployment
```

No modo de implantação , o Bundler irá "lançar" o pacote para produção ou uso de CI. Verifique com atenção se deseja que esta opção seja ativada em seu ambiente de desenvolvimento.

```ruby
--force
```

Força baixar todas as gemas, mesmo que as versões necessárias já estejam disponíveis localmente.

```ruby
--frozen
```

Não permita que o Gemfile.lock seja atualizado após essa instalação. Sai não-zero se houver mudanças no Gemfile.lock.

```ruby
--full-index
```

O Bundler não chamará o ponto final da API da Rubygems (padrão), mas baixará e armazena em cache um arquivo de índice (atualmente grande) de todas as gemas. O desempenho pode ser melhorado para pacotes grandes que raramente mudam ao ativar esta opção.

```ruby
--gemfile=<gemfile>
```

A localização do Gemfile (5) que o Bundler deve usar. Este padrão é um Gemfile (5) no diretório de trabalho atual. Em geral, o Bundler assumirá que a localização do Gemfile (5) também é a raiz do projeto e tentará encontrar Gemfile.locke em vendor/cacherelação a esse local.

```ruby
--jobs=[<number>], -j[<number>]
```
O número máximo de trabalhos paralelos de download e instalação. O padrão é 1.

```ruby
--local
```

Não tente se conectar rubygems.org. Em vez disso, o Bundler usará as gemas já presentes no cache de Rubygems ou dentro vendor/cache. Tenha em atenção que, se existir uma gem específica específica da plataforma, rubygems.orgela não será encontrada.

```ruby
--no-cache
```

Não atualize o cache vendor/cachecom as gemas recém-juntas. Isso não remove gemas no cache, mas mantém as gemas recém-agrupadas a serem armazenadas em cache durante a instalação.

```ruby
--no-prune
```

Não remova gemas obsoletas do cache quando a instalação terminar.

```ruby
--path=<path>
```

A localização para instalar as gemas especificadas. Este padrão é a configuração do Rubygems. Bundler compartilha esta localização com Rubygems, gem install ...também terá gem instalado lá. Portanto, gemas instaladas sem uma --path ...configuração aparecerão ligando gem list. Consequentemente, as gemas instaladas em outros locais não serão listadas.

```ruby
--quiet
```

Não imprima informações de progresso na saída padrão. Em vez disso, o Bundler irá sair usando um código de status ( $?).

```ruby
--retry=[<number>]
```

Tente novamente as solicitações de rede ou git com falha para o número de vezes.

```ruby
--shebang=<ruby-executable>
```

Usa o executável ruby ​​especificado (geralmente ruby) para executar os scripts criados com --binstubs. Além disso, se você usar --binstubsjunto com --shebang jrubyesses executáveis ​​será alterado para executar em jruby vez disso.

```ruby
--standalone[=<list>]
```

Faz um pacote que pode funcionar sem depender de Rubygems ou Bundler no tempo de execução. É necessário especificar uma lista separada de espaços para instalar. O Bundler cria um diretório chamado bundlee instala o pacote lá. Ele também gera um bundle/bundler/setup.rbarquivo para substituir a própria instalação do Bundler da maneira requerida. Usar esta opção implícitamente define path, que é uma [opção lembrada] [OPÇÕES RECEBIDAS].

```ruby
--system
```

Instala as gemas especificadas no pacote para a localização do Rubygems do sistema. Isso substitui qualquer configuração anterior de --path.

```ruby
--trust-policy=[<policy>]
```

Aplicar a política de segurança Rubygems política , onde a política é um dos HighSecurity, MediumSecurity, LowSecurity, AlmostNoSecurity, ou NoSecurity. Para obter mais detalhes, consulte a documentação de assinatura da Rubygems, ligada abaixo, em VER TAMBÉM .

```ruby
--with=<list>
```

Uma lista separada por espaço de grupos referentes a gemas para instalar. Se for dado um grupo opcional, ele está instalado. Se for dado um grupo que esteja na lista lembrada de grupos atribuídos a - sem, ele é removido dessa lista.

```ruby
--without=<list>
```

Uma lista de grupos separados por espaços referentes a gemas para ignorar durante a instalação. Se for dado um grupo que esteja na lista lembrada de grupos atribuídos a - com, ele será removido dessa lista.
