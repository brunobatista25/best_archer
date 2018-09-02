## Realizando Açōes

## attach_file

Encontre um campo de arquivo na página e anexe um arquivo ao seu caminho.

```ruby
page.attach_file(locator, '/path/to/file.png')
```

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

## fill_in

Localize um campo de texto ou área de texto e preencha-o com o texto fornecido O campo pode ser encontrado através do seu nome, identificação ou texto da etiqueta.

```ruby
fill_in 'Name', with: 'Bob'
```

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












## Simple

#[](name) ⇒ String
Retrieve the given attribute.

element[:title] # => HTML title attribute
Parameters:

name (Symbol) — The attribute name to retrieve

#allow_reload! ⇒ Object
#checked? ⇒ Boolean
Whether or not the element is checked.
#disabled? ⇒ Boolean
Whether or not the element is disabled.
#find_css(css) ⇒ Object private
#find_xpath(xpath) ⇒ Object private
#initialize(native) ⇒ Simple constructor
A new instance of Simple.
#inspect ⇒ Object
#path ⇒ String
An XPath expression describing where on the page the element can be found.
#selected? ⇒ Boolean
Whether or not the element is selected.
#session_options ⇒ Object private
#synchronize(_seconds = nil) ⇒ Object
#tag_name ⇒ String
The tag name of the element.
#text(_type = nil) ⇒ String
The text of the element.
#title ⇒ String
The title of the document.
#value ⇒ String
The value of the form element.
#visible?(check_ancestors = true) ⇒ Boolean
Whether or not the element is visible.


## Element

#[](attribute) ⇒ String
Retrieve the given attribute.
#allow_reload! ⇒ Object
#checked? ⇒ Boolean
Whether or not the element is checked.
#click(*key_modifiers = [], offset = {x: nil, y: nil}) ⇒ Capybara::Node::Element
Click the Element.
#disabled? ⇒ Boolean
Whether or not the element is disabled.
#double_click(*key_modifiers = [], offset = {x: nil, y: nil}) ⇒ Capybara::Node::Element
Double Click the Element.
#drag_to(node) ⇒ Capybara::Node::Element
Drag the element to the given other element.
#hover ⇒ Capybara::Node::Element
Hover on the Element.
#initialize(session, base, query_scope, query) ⇒ Element constructor
A new instance of Element.
#inspect ⇒ Object
#multiple? ⇒ Boolean
Whether or not the element supports multiple results.
#native ⇒ Object
The native element from the driver, this allows access to driver specific methods.
#path ⇒ String
An XPath expression describing where on the page the element can be found.
#readonly? ⇒ Boolean
Whether or not the element is readonly.
#reload ⇒ Object
#right_click(*key_modifiers = [], offset = {x: nil, y: nil}) ⇒ Capybara::Node::Element
Right Click the Element.
#select_option ⇒ Capybara::Node::Element
Select this node if is an option element inside a select tag.
#selected? ⇒ Boolean
Whether or not the element is selected.
#send_keys(keys, ...) ⇒ Capybara::Node::Element
Send Keystrokes to the Element.

Symbols supported for keys :cancel :help :backspace :tab :clear :return :enter :shift :control :alt :pause :escape :space :page_up :page_down :end :home :left :up :right :down :insert :delete :semicolon :equals :numpad0 :numpad1 :numpad2 :numpad3 :numpad4 :numpad5 :numpad6 :numpad7 :numpad8 :numpad9 :multiply - numeric keypad * :add - numeric keypad + :separator - numeric keypad 'separator' key ?? :subtract - numeric keypad - :decimal - numeric keypad . :divide - numeric keypad / :f1 :f2 :f3 :f4 :f5 :f6 :f7 :f8 :f9 :f10 :f11 :f12 :meta :command - alias of :meta

#set(value, **options) ⇒ Capybara::Node::Element
Set the value of the form element to the given value.
#tag_name ⇒ String
The tag name of the element.
#text(type = nil) ⇒ String
Retrieve the text of the element.
#trigger(event) ⇒ Capybara::Node::Element
Trigger any event on the current element, for example mouseover or focus events.
#unselect_option ⇒ Capybara::Node::Element
Unselect this node if is an option element inside a multiple select tag.
#value ⇒ String
The value of the form element.
#visible? ⇒ Boolean
Whether or not the element is visible.