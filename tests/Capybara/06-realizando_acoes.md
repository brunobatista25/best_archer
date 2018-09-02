## Realizando Açōes

-------------------------------------------------------------------------------

## Preenchendo campos

## fill_in

Localize um campo de texto ou área de texto e preencha-o com o texto fornecido O campo pode ser encontrado através do seu nome, identificação ou texto da etiqueta.

```ruby
fill_in 'Name', with: 'Bob'
```

## .send_keys

Enviar pressionamentos de tecla para o elemento.

```ruby
find('elemento').send_keys('bruno')
```

## .set 

Defina o valor do elemento de formulário para o valor fornecido.

```ruby
find('elemento').set('bruno')
```

-------------------------------------------------------------------------------
## Clicando em elementos

## click_button

Encontra um botão na página e clica nele.

```ruby
click_button('botao')
```

## click_link

Encontra um link por id, texto ou título e clica nele.

```ruby
click_link('link')
```

## click_link_or_button

Encontra um botão ou link e clica nele.

```ruby
click_link_or_button('linkoubotao')
```

## .double_click

Clique duas vezes no elemento.

```ruby
find('botao').double_click
```

## .click

Clique no elemento.

```ruby
find('botao').click
```

## .right_click

Clique com o botão direito no elemento.

```ruby
find('botao').right_click
```

-------------------------------------------------------------------------------
## RadioBox e CheckBox

## check

Encontre uma caixa de seleção e marque-a como marcado.

```ruby
page.check('German')
```

## uncheck

Encontre uma caixa de seleção e marque a caixa de seleção.

```ruby
uncheck('German')

```

## choose

Encontre um botão de opção e marque-o como marcado.

```ruby
page.choose('Male')
```

-------------------------------------------------------------------------------
## Upload de Arquivo

## attach_file

Encontre um campo de arquivo na página e anexe um arquivo ao seu caminho.

```ruby
page.attach_file(locator, '/path/to/file.png')
```

-------------------------------------------------------------------------------

## Drag and Drop

## .drag_to

Move um elemento para outra posição

```ruby
  @primeiro_elemento = find('#winston')
  @segundo_elemento = find('#dropzone')
  @primeiro_elemento.drag_to(@segundo_elemento)
```

-------------------------------------------------------------------------------

## Mousehover

## .hover

Passe o mouse sobre o elemento.

```ruby
find('elemento').hover

find('.activator').hover.click
```

-------------------------------------------------------------------------------

## Combobox

## select

Se a opção `:from` estiver presente, o `select` encontra uma caixa de seleção na página e seleciona uma opção particular dela. Caso contrário, ele encontrará uma opção dentro do escopo atual e a selecionará. Se a caixa de seleção for uma seleção múltipla, selecione pode ser chamado várias vezes para selecionar mais de uma opção. A caixa de seleção pode ser encontrada pelo nome, identificação ou texto da etiqueta. A opção pode ser encontrada pelo seu texto.

```ruby
select 'March', from: 'Month'
```

## unselect

Encontre uma caixa de seleção na página e desmarque uma opção específica dela.

```ruby
unselect 'March', from: 'Month'
```

## .select_option

Selecione este nó se for um elemento de opção dentro de uma tag de seleção.

```ruby
find('opcao').select_option
```

## .unselect_option

Desmarque este nó se for um elemento de opção dentro de uma tag de seleção múltipla.

```ruby
find('opcao').unselect_option
```

-------------------------------------------------------------------------------
## Opçōes para auxiliares para açōes.

**Essas opçōes não são para todos o comandos não, sugiro ir na domcumentação e ver qual comando comando usa as opcōes nesse** [Link](https://www.rubydoc.info/github/teamcapybara/capybara/master/Capybara/Node/Actions)

**:allow_label_click**  - Tenta clicar no rótulo para alternar o estado se o elemento não estiver visível.

**:class** - Campos de correspondência que correspondem à (s) classe (s) fornecida (s)

**:class** - Corresponder campos que correspondam à (s) classe (s) fornecida (s)
make_visible (true, Hash) - Um Hash de estilos CSS para alterar antes de tentar anexar o arquivo, se `true` {opacity: 1, display: 'block', visibilidade: 'visible'} é usado (pode não ser suportado por todos os drivers)
*exact* - Corresponda o nome / conteúdo exato da etiqueta ou aceite uma correspondência parcial.

**:currently_with** — A propriedade de valor atual do campo para preencher

**:fill_options** — Opções específicas do driver sobre como preencher campos

**:from** — O id, nome ou rótulo da caixa de seleção

**id** - Corresponder campos que correspondem ao atributo id

**match** - A estratégia de correspondência a ser usada (:one,:first,:prefer_exact,:smart).

**multiple** - Campo de correspondência que permite a seleção de vários arquivos.

**name** - Corresponder campos que correspondem ao atributo name

**:option** (String) — Valor da caixa de seleção para selecionar

**:option** — Valor do radio_button para escolher

**:placeholder** — Corresponder campos que correspondam ao atributo de espaço reservado

**wait** - Tempo máximo para aguardar a exibição do elemento correspondente.

**:with** — O valor a preencher - obrigatório

**Vamos para o próximo post** [Validando elementos](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/07-validando_elementos.md);

--------------------------------------------------------------------------------
