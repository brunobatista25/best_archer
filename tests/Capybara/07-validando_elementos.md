## Matchers

------------------------------------------------------------------------------
## Asserts

## assert_all_of_selectors

Afirma que todos os seletores fornecidos estão presentes na página ou nos descendentes do nó atual.

```ruby
page.assert_all_of_selectors('elemento')
```

## assert_none_of_selectors

Afirma que nenhum dos seletores fornecidos está presente na página ou nos descendentes do nó atual.

```ruby
page.assert_none_of_selector('elemento')
```

## assert_matches_selector

Afirma que o current_node corresponde a um determinado seletor.

```ruby
page.assert_matches_selector('elemento')
```
 
## assert_selector

Afirma que um determinado seletor está na página ou um descendente do nó atual.

```ruby
page.assert_selector('elemento')
```

## assert_text

Afirma que a página ou o nó atual possui o conteúdo de texto especificado, ignorando quaisquer tags HTML.

```ruby
page.assert_text('elemento')
```

## assert_title

Afirma que a página tem o título dado.

```ruby
page.assert_title('titulo')
```

-------------------------------------------------------------------------------
## Asserts de negação

## assert_not_matches_selector

Afirma que o current_node não corresponde a um determinado seletor.

```ruby
page.assert_not_matches_selector('elemento')
```

## assert_no_selector

Afirma que um determinado seletor não está na página ou descendente do nó atual..

```ruby
page.assert_no_selector('elemento')
```

## assert_no_text

Afirma que a página ou o nó atual não tem o conteúdo de texto especificado, ignorando quaisquer tags HTML.

```ruby
page.assert_no_text('elemento')
```

## assert_no_title

Afirma que a página não tem o título dado.

```ruby
page.assert_no_title('titulo')
```

-------------------------------------------------------------------------------

## Validaçōes com Has

## has_checked_field?

Verifica se a página ou o nó atual tem um botão de opção ou caixa de seleção com o rótulo, valor ou ID fornecido, que está atualmente marcado.

```ruby
page.has_checked_field?('elemento')
```

## has_select?

Verifica se a página ou o nó atual tem um campo de seleção com o rótulo, o nome ou o ID fornecido.

```ruby
page.has_select?('elemento')
```

## has_selector?

Verifica se um determinado seletor está na página ou um descendente do nó atual.

```ruby
page.has_selector?('elemento')
```

## has_table?

Verifica se a página ou o nó atual possui uma tabela com o ID ou a legenda especificada

```ruby
page.has_table?('elemento')
```

## has_text?

Verifica se a página ou o nó atual tem o conteúdo de texto especificado, ignorando todas as tags HTML.

```ruby
page.has_text?('elemento')
```

## has_button?

Verifica se a página ou o nó atual possui um botão com o texto, valor ou id fornecido.

```ruby
page.has_button?('elemento')
```

## has_unchecked_field?

Verifica se a página ou o nó atual tem um botão de opção ou caixa de seleção com o rótulo, valor ou ID fornecido, que está atualmente desmarcado.

```ruby
page.has_unchecked_field?('elemento')
```

## has_xpath?

Verifica se uma determinada expressão XPath está na página ou um descendente do nó atual.

```ruby
page.has_xpath?('elemento')
```

## has_css?

Verifica se um determinado seletor de CSS está na página ou um descendente do nó atual.

```ruby
page.has_css?('elemento')
```

## has_field?

Verifica se a página ou o nó atual tem um campo de formulário com o rótulo, o nome ou o ID fornecido.

```ruby
page.has_field?('elemento')
```

## has_link?

Verifica se a página ou o nó atual tem um link com o texto ou o ID fornecido.

```ruby
page.has_link?('elemento')
```

## has_title?

Afirma que a página tem o título dado.

```ruby
page.has_title?('titulo')
```

-------------------------------------------------------------------------------

## Negaçōes com Has_no


## has_no_title?

Verifica se a página não tem o título dado.

```ruby
page.has_no_title('titulo')
```

## has_no_button?

Verifica se a página ou o nó atual não possui um botão com o texto, valor ou id fornecido.

```ruby
page.has_no_button?('elemento')
```

## has_no_checked_field?

Verifica se a página ou o nó atual não tem nenhum botão de opção ou caixa de seleção com o rótulo, valor ou ID fornecido, que está atualmente marcado.

```ruby
page.has_no_checked_field?('elemento')
```

## has_no_css?

Verifica se um determinado seletor de CSS não está na página ou um descendente do nó atual.

```ruby
page.has_no_css?('elemento')
```

## has_no_field?

Verifica se a página ou o nó atual não possui um campo de formulário com o rótulo, nome ou ID fornecido.

```ruby
page.has_no_field?('elemento')
```

## has_no_link?

Verifica se a página ou o nó atual não tem link com o texto ou o ID fornecido.

```ruby
page.has_no_link?('elemento')
```

## has_no_select?

Verifica se a página ou o nó atual não tem campo de seleção com o rótulo, nome ou id fornecido.

```ruby
page.has_no_select?('elemento')
```

## has_no_selector?

Verifica se um determinado seletor não está na página ou um descendente do nó atual.

```ruby
page.has_no_selector?('elemento')
```

## has_no_table?

Verifica se a página ou o nó atual não possui tabela com o ID ou legenda especificada.

```ruby
page.has_no_table?('elemento')
```

## has_no_text?

Verifica se a página ou o nó atual não possui o conteúdo de texto especificado, ignorando qualquer tag HTML e normalizando o espaço em branco.

```ruby
page.has_no_text?('elemento')
```

## has_no_unchecked_field?

Verifica se a página ou o nó atual não tem botão de opção ou caixa de seleção com o rótulo, valor ou ID fornecido, que está atualmente desmarcado.

```ruby
page.has_no_unchecked_field?('elemento')
```

## has_no_xpath?

Verifica se uma determinada expressão XPath não está na página ou descendente do nó atual.

```ruby
page.has_no_xpath?('elemento')
```

-------------------------------------------------------------------------------

## Validando com matches_css

## matches_css?

Verifica se o nó atual corresponde ao seletor de CSS especificado.

```ruby
page.matches_css?('elemento')
@element = find('elemento')
expect(@element).to matches_css('elemento')
expect(@element.matches_css?('elemento')).to be true
```

## matches_selector?

Verifica se o nó atual corresponde ao seletor especificado.

```ruby
page.matches_selector?('elemento')
@element = find('elemento')
expect(@element).to matches_selector('elemento')
expect(@element.matches_selector?('elemento')).to be true
```

## matches_xpath?

Verifica se o nó atual corresponde a determinada expressão XPath.

```ruby
page.matches_xpath?('elemento')
@element = find('elemento')
expect(@element).to matches_xpath('elemento')
expect(@element.matches_xpath?('elemento')).to be true
```

------------------------------------------------------------------------------

## Negando com not_matches

## not_matches_css?

Verifica se o nó atual não corresponde ao seletor de CSS fornecido.

```ruby
page.not_matches_css?('elemento')
@element = find('elemento')
expect(@element).to not_matches_css('elemento')
expect(@element.not_matches_css?('elemento')).to be true
```

## not_matches_selector?
Verifica se o nó atual não corresponde ao dado seletor. O uso é idêntico ao has_selector?.

```ruby
page.not_matches_selector?('elemento')
@element = find('elemento')
expect(@element).to not_matches_selector('elemento')
expect(@element.not_matches_selector?('elemento')).to be true
```

## not_matches_xpath?

Verifica se o nó atual não corresponde à expressão XPath fornecida.

```ruby
page.not_matches_xpath?('elemento')
@element = find('elemento')
expect(@element).to not_matches_xpath('elemento')
expect(@element.not_matches_xpath?('elemento')).to be true
```

-------------------------------------------------------------------------------

## Opçōes para auxiliares para matchers.

** Essas opçōes não são para todos o comandos não, sugiro ir na domcumentação e ver qual comando comando usa as opcōes nesse [Link](https://www.rubydoc.info/github/teamcapybara/capybara/master/Capybara/Node/Matchers)


**:count** — Número de vezes que o texto deve ocorrer

**:minimum** — Número mínimo de vezes que o texto deve ocorrer

**:maximum** — Número máximo de vezes que o texto deve ocorrer

**:between** — Intervalo de horas que deve conter o número de vezes que o texto ocorre

**:wait** — Tempo máximo que o Capybara esperará pelo texto para eq/match dado o argumento string/regexp

**:exact** — Se o texto deve ser uma correspondência exata ou apenas substring

**:with** — O conteúdo de texto do campo ou um Regexp para corresponder

**:type** — O atributo type do campo

**:options** — Opções que devem estar contidas nesta caixa de seleção

**:with_options** — Conjunto parcial de opções que devem estar contidas nesta caixa de seleção

**:selected** — Opções que devem ser selecionadas

**:with_selected** — Conjunto parcial de opções que devem ser minimamente selecionadas

**Vamos para o próximo post** [Validando elementos com rspec matchers](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/08-validando_com_rspec_matchers.md);

-------------------------------------------------------------------------------