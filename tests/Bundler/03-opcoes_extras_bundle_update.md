#Opções para bundle update

```ruby
--group=<name>, -g=[<name>]
```

Apenas atualize as gemas no grupo especificado. Por exemplo, você pode atualizar todas as gemas no grupo de desenvolvimento com bundle update --group development. Você também pode ligar bundle update rails --group testpara atualizar a jóia dos trilhos e todas as gemas no grupo de teste, por exemplo.

```ruby
--source=<name>
```

O nome de uma :gitou :pathfonte usada no Gemfile (5) . Por exemplo, com uma :gitfonte de http://github.com/rails/rails.git, você ligariabundle update --source rails

```ruby
--local
```

Não tente obter gemas remotamente e use o cache de gema em vez disso.

```ruby
--ruby
```

Atualize a versão bloqueada do Ruby para a versão atual do Ruby.

```ruby
--bundler
```

Atualize a versão bloqueada do bundler para a versão do bundler invocado.

```ruby
--full-index
```

Volte a usar o índice de arquivo único de todas as gemas.

```ruby
--jobs=[<number>], -j[<number>]
```

Especifique o número de trabalhos a serem executados em paralelo. O padrão é 1.

```ruby
--retry=[<number>]
```

Tente novamente as solicitações de rede ou git com falha para o número de vezes.

```ruby
--quiet
```

Apenas avisos e erros de saída.

```ruby
--force
```

Force baixar todas as gemas.

```ruby
--patch
```

Prefira atualizar apenas para a próxima versão do patch.

```ruby
--minor
```

Prefere atualizar apenas para a próxima versão secundária.

```ruby
--major
```

Prefira atualizar para a próxima versão principal (padrão).

```ruby
--strict
```

Não permita que nenhuma jóia seja atualizada mais recente --patch| --minor| --major.

```ruby
--conservative
```

Use o comportamento da atualização conservadora da instalação do pacote e não permita que as dependências compartilhadas sejam atualizadas.
