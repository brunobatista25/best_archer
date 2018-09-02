## Validando com Rspec Matcher
 
-------------------------------------------------------------------------------

## have_all_of_selectors

Verifica se os elementos correspondentes a um grupo de seletores existem .

```ruby
expect(@elemento).to have_all_of_selectors('//p')
```

## have_button
Verifica se a página ou o nó atual possui um botão com o texto, valor ou id fornecido.

```ruby
expect(@elemento).to have_button('//p')
```

## have_checked_field
Se a página ou o nó atual tiver um botão de opção ou uma caixa de seleção com o rótulo, valor ou ID fornecido, que está marcado no momento.

```ruby
expect(@elemento).to have_checked_field('//p')
```

## have_css
Verifica se um determinado seletor de CSS está na página ou um descendente do nó atual.

```ruby
expect(@elemento).to have_css('//p')
```

## have_current_path
Afirma que a página tem o caminho fornecido

```ruby
expect(@elemento).to have_current_path('//p')
```

## have_field
Verifica se a página ou o nó atual tem um campo de formulário com o rótulo, o nome ou o ID fornecido.

```ruby
expect(@elemento).to have_field('//p')
```

## have_link

Verifica se a página ou o nó atual tem um link com o texto ou o ID fornecido.

```ruby
expect(@elemento).to have_link('//p')
```

## have_none_of_selectors

Afirma que nenhum dos seletores fornecidos está presente na página ou nos descendentes do nó atual.

```ruby
expect(@elemento).to have_none_of_selectors('//p')
```

## have_select

Verifica se a página ou o nó atual tem um campo de seleção com o rótulo, o nome ou o ID fornecido.

```ruby
expect(@elemento).to have_select('//p')
```

## have_selector

Afirma que um determinado seletor está na página ou um descendente do nó atual.

```ruby
expect(@elemento).to have_selector('//p')
```

## have_table

Verifica se a página ou o nó atual tem uma tabela com o ID ou legenda fornecida

```ruby
expect(@elemento).to have_table('//p')
```

## have_text

Afirma que a página ou o nó atual possui o conteúdo de texto especificado, ignorando quaisquer tags HTML.

```ruby
expect(@elemento).to have_text('//p')
```

## have_title

Verifica se um determinado título esta na página.

```ruby
expect(@elemento).to have_title('//p')
```

## have_unchecked_field

Verifica se uma determinada expressão XPath está na página ou um descendente do nó atual.

```ruby
expect(@elemento).to have_unchecked_field('//p')
```

## have_xpath

Verifica se uma quantia determinada XPath está na página ou descendente do seu atual.

```ruby
expect(@elemento).to have_xpath('//p')
```


## match_css

Afirma que o current_node corresponde a um determinado seletor

```ruby
expect(find('#zone')).to match_css('elemento')
```

## match_selector

 Afirma que o current_node corresponde a um determinado seletor

```ruby
expect(find('#zone')).to match_selector('elemento')
```

## match_xpath

Correspondente RSpec para saber se o elemento atual corresponde a um determinado seletor de xpath.

```ruby
expect(find('#zone')).to match_xpath('elemento')
```

-------------------------------------------------------------------------------


**Vamos para o próximo post** [Janelas, Modal, Alerts e Iframe](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/09-janelas_modal_alerts_iframe.md);