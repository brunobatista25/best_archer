# Capybara

## Introdução

Capybara é um framework de automação de testes em aplicações web, open-source, e escrito em Ruby. É utilizado para testar as aplicações simulando as ações que os usuários reais executariam na aplicação. Para utilizar o Capybara é necessário ter instalado o [Ruby](https://github.com/brunobatista25/best_archer/blob/master/tests/ConfiguracaoRuby/configuracao_ruby.md); 

------------------------------------------------------------------------------
# Instalando os Drivers

## Chromedriver

O ChromeDriver é um servidor autônomo que implementa o protocolo de fio da WebDriver para o Chromium, que está disponível para o Chrome no Android e no Chrome na área de trabalho (Mac, Linux, Windows e ChromeOS)
> Download: https://bit.ly/2e6e5sz

## GeckoDriver

Gecko Driver é a conexão entre seus testes em Selenium e o programa Firefox. Clientes compatíveis para interagir com navegadores baseados em Gecko, ou seja, Mozilla Firefox para esta situação.
> Download: https://bit.ly/2joYOJD

## PhantomJS

PhantomJS é basicamente um browser sem interface gráfica baseado no WebKit (similar ao Safari e Google Chrome), onde você roda em background e manipula via API JavaScript. A vantagem de usar o PhantomJS é que ele é compátivel com qualquer sistema de poder ser instalado em qualquer máquina.
> Download: https://bit.ly/2re71RE

## Instalando ChromeDriver, GeckoDriver e PhantomJS no Windows 

> Temos duas opções de instalação dos drivers

**Instalação manual**

  1. Baixe os respectivos drivers nos links de download logo acima.
  2. Se necessário, extraia o arquivo .exe para alguma pasta do seu desktop.
  3. Coloque os executáveis dentro da pasta **C:\Windows** e *voilà*
  
**Instalação via NPM** 

  1. Baixe o NodeJs no site https://bit.ly/1LjG5AH e execute a instalação
  2. Para verificar se a instalação foi um sucesso, abra o PowerShell ou CMDER e digite os seguintes comandos:
	`node -v` 
    `npm -v`
		>Você deve receber de retorno as versões das ferramentas.
  4. Com o PowerShell ou CMDER aberto, para instalar o GeckoDriver, o ChromeDriver e o PhantomJS, digite:
	 > GeckoDriver
    `npm install -g geckodriver `
    
	 > ChromeDriver
    `npm install -g chromedriver`
    
   > PhantomJS
    `npm install -g phantomjs-prebuilt`


## Instalando ChromeDriver, GeckoDriver e PhamtomJS no Mac:

A instalação no MacOS, assim como no Linux, é ainda mais fácil.

1. Abra o terminal e instale o HomeBrew com o comando:
	```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```

2. Para verificar se o HomeBrew foi instalado corretamente, digite **which brew**. Você deverá ver algo como:
	>**/usr/local/bin/brew**
	
3. Para instalar o GeckoDriver, o ChromeDriver e o PhantomJs, digite:
	 > GeckoDriver
    `brew install geckodriver `
    
	 > ChromeDriver
    `brew install chromedriver`
    
  	 > PhantomJS
    `brew install phantomjs`

## Instalando ChromeDriver, GeckoDriver e PhantomJS no Linux:

Para instalar os drivers no Linux, podemos usar o mesmo método do NPM. Apenas uma observação que o Linux possui algumas particuladores na hora de instalar o Node. Basta seguir este guia https://bit.ly/2HD54sW que vai dar tudo certo! 
  1. Com o Terminal aberto, para instalar o GeckoDriver, o ChromeDriver e o PhantomJS, digite:
	 > GeckoDriver
    `npm install -g geckodriver `
    
	 > ChromeDriver
    `npm install -g chromedriver`
    
  	 > PhantomJS
    `npm install -g phantomjs-prebuilt`
------------------------------------------------------------------------------
# Configuração

Agora vamos configurar nosso projeto ruby com capybara

Primeiro vc precisa ter instalado o [Bundler](https://github.com/brunobatista25/best_archer/blob/master/tests/Bundler/01-introducao_bundler.md)


Agora crie um arquivo  chamado Gemfile sem nenhuma extensão, agora dentro do arquivo coloque os seguintes conteúdos:

```
source 'http://rubygems.org'

gem 'capybara'
gem 'selenium-webdriver'
```

Essa são as gems minímas para se configurar o projeto com capybara

Capybara será o framework de desenvolvimento.

Selenium Webdriver será o Driver base e abrir o Chrome para automação.

Agora rode o comando

```
bundle install
```

Todas a gems serão instaladas e um outro arquivo sera criado automaticamente Gemfile.lock

## Configurando o ENV.RB

Dentro desse arquivo temos que especificar as gems que serão utilizadas

```
require 'capybara'
require 'selenium-webdriver'
```

## Agora iremos adicionar umas configurações do capybara neste mesmo arquivo:

```ruby
require 'capybara'
require 'selenium-webdriver'

Capybara.configure do |config|
  config.default_driver = :selenium
  config.app_host = "https://www.google.com/"
  config.default_max_wait_time = 30
end
```

```ruby
#Estou definindo que o driver que vou utilizar e o selenium webdriver.
Capybara.default_driver = :selenium 
```

```ruby
#Esse comando e a configuraçaão para qual tempo minímo para esperar um elemento na tela
Capybara.default_max_wait_time = 30 
```

```ruby
#Aqui configuro qual url so site que estou usando
Capybara.app_host
```

## Configurar qual navegador  usar para automação

Dentro deste mesmo arquivo iremos colocar a configuração de qual navegador iremos usar

## Chrome


Para usar o chrome basta usar a seguinte configuração

```ruby
require 'capybara'
require 'selenium-webdriver'

Capybara.configure do |config|
  config.default_driver = :selenium_chrome
  config.app_host = "https://www.google.com/"
  config.default_max_wait_time = 30
end
```

ou

```ruby
require 'capybara'
require 'selenium-webdriver'

Capybara.register_driver :selenium do |app|
  Capybara::Selenium::Driver.new(app, browser: :chrome)
end

Capybara.configure do |config|
  config.default_driver = :selenium
  config.app_host = "https://www.google.com/"
  config.default_max_wait_time = 30
end

```

## Firefox

Para usar o firefox basta usar a seguinte configuração

```ruby
require 'capybara'
require 'selenium-webdriver'

Capybara.configure do |config|
  config.default_driver = :selenium
  config.app_host = "https://www.google.com/"
  config.default_max_wait_time = 30
end
```

```ruby
require 'capybara'
require 'selenium-webdriver'

Capybara.register_driver :selenium do |app|
  Capybara::Selenium::Driver.new(app, browser: :firefox)
end

Capybara.configure do |config|
  config.default_driver = :selenium
  config.app_host = "https://www.google.com/"
  config.default_max_wait_time = 30
end
```

# Navegação

## Visit
Você pode usar o método de "visit" para navegar para outras páginas:
O método de visit só aceita um único parâmetro, o método de solicitação é sempre GET.

```
visit('https://www.site.com.br')
```

## have_current_path

Você pode obter o caminho atual da sessão de navegação e testá-lo usando o have_current_path correspondente:

```ruby
expect(page).to have_current_path('https://www.site.com.br', url: true)
```
------------------------------------------------------------------------------

# Buscando Elementos

Você também pode encontrar elementos específicos, a fim de manipulá-los:

## all

Encontre todos os elementos na página que correspondem ao seletor e opções fornecidos.

```ruby
page.all(:css, 'elemento')
```

## ancestor

Encontre um elemento com base nos argumentos fornecidos que também é um ancestral do elemento chamado.

```ruby
element.ancestor('#foo').find('.bar')
```

## find

Encontre um elemento com base nos argumentos fornecidos.

```ruby
find('elemento')
```

## find_button

Encontre um botão na página.

```ruby
find_button('elemento_do_botao')
```

## find_by_id

Encontre um elemento na página, dado seu id.

```ruby
find_by_id('id_do_elemento')
```

## find_field

Encontre um campo de formulário na página.

```ruby
find_field('elemento')
```

## find_link

Encontre um link na página.

```ruby
find_link('link_do_elemento')
```

## first

Encontre o primeiro elemento na página que corresponda ao seletor e opções fornecidos.

```ruby
first('elemento')
```

## sibling

Encontre um elemento baseado nos argumentos dados que também é um irmão do elemento chamado.

```ruby
element.sibling('elemento')
```

## Opçōes para auxiliares para buscas.

** Essas opçōes não são para todos o comandos não, sugiro ir na domcumentação e ver qual comando comando usa as opcōes nesse [Link](https://www.rubydoc.info/github/teamcapybara/capybara/master/Capybara/Node/Finders)


*:all* - encontra um campo ativado ou desativado

*alt* - Corresponder links com um elemento img contido, cujo alt corresponde

*between* - O número de correspondências encontradas deve estar dentro do intervalo determinado

*checked* - Corresponder campo verificado?

*class* - Corresponder links que correspondam à (s) classe (s) fornecida (s)

*count* - Número exato de correspondências que se espera encontrar

*disabled* - padrão: false - Corresponder campo desativado?

*exact* - Controlar se as expressões `is` no determinado XPath correspondem exatamente ou parcialmente

*exact_text* - Quando String, o texto contido no elemento deve corresponder exatamente, quando o Boolean controla se a opção: text deve corresponder exatamente

*false* - só encontra um campo ativado

*:hidden* - só encontra elementos invisíveis.

*href* - Valor para combinar com os links href, se nil encontrar espaços reservados para links (<a> elementos sem atributo href)

*id* - Corresponder links com o ID fornecido

*match* - A estratégia de correspondência a ser usada.

*maximum* - Número máximo de correspondências que se espera encontrar

*minimum* - Número mínimo de correspondências que se espera encontrar

*multiple* - Corresponder campos que podem ter vários valores?

*name* - Corresponder campos que correspondem ao atributo name

*placeholder* - Corresponder campos que correspondam ao atributo de espaço reservado

*readonly* - Corresponder campo readonly?

*text* - Apenas encontre elementos que contenham este texto ou correspondam a este regexp

*title* - Corresponder links com o título fornecido

*true* - só encontra um campo desativado

*type* - Tipo de campo para combinar

*unchecked* - Corresponder campo desmarcado?

*value* - Corresponder botões com o valor fornecido

*visible* - Apenas encontre elementos com a visibilidade especificada:

*:visible* - o mesmo que true; só encontra elementos visíveis.

*wait* - Tempo máximo para aguardar a exibição do elemento correspondente.

*with* - Valor do campo para combinar
------------------------------------------------------------------------------

## Realizando Açōes

#attach_file
Encontre um campo de arquivo na página e anexe um arquivo ao seu caminho.

```ruby
page.attach_file(locator, '/path/to/file.png')
```

#check
Encontre uma caixa de seleção e marque-a como marcado.

```ruby
page.check('German')
```

#uncheck
Encontre uma caixa de seleção e marque a caixa de seleção.

```ruby
uncheck('German')

```

#choose
Encontre um botão de opção e marque-o como marcado.

```ruby
page.choose('Male')
```

#click_button
Encontra um botão na página e clica nele.

```ruby
click_button('botao')
```

#click_link
Encontra um link por id, texto ou título e clica nele.

```ruby
click_link('link')
```

#click_link_or_button
Encontra um botão ou link e clica nele.

```ruby
click_link_or_button('linkoubotao')
```

#fill_in
Localize um campo de texto ou área de texto e preencha-o com o texto fornecido O campo pode ser encontrado através do seu nome, identificação ou texto da etiqueta.

```ruby
fill_in 'Name', with: 'Bob'
```

#select
Se a opção `:from` estiver presente, o `select` encontra uma caixa de seleção na página e seleciona uma opção particular dela. Caso contrário, ele encontrará uma opção dentro do escopo atual e a selecionará. Se a caixa de seleção for uma seleção múltipla, selecione pode ser chamado várias vezes para selecionar mais de uma opção. A caixa de seleção pode ser encontrada pelo nome, identificação ou texto da etiqueta. A opção pode ser encontrada pelo seu texto.

```ruby
select 'March', from: 'Month'
```

#unselect
Encontre uma caixa de seleção na página e desmarque uma opção específica dela.

```ruby
unselect 'March', from: 'Month'
```

## Opçōes para auxiliares para açōes.

** Essas opçōes não são para todos o comandos não, sugiro ir na domcumentação e ver qual comando comando usa as opcōes nesse [Link](https://www.rubydoc.info/github/teamcapybara/capybara/master/Capybara/Node/Actions)

*:allow_label_click*  - Tenta clicar no rótulo para alternar o estado se o elemento não estiver visível.

*:class* - Campos de correspondência que correspondem à (s) classe (s) fornecida (s)

*:class* - Corresponder campos que correspondam à (s) classe (s) fornecida (s)
make_visible (true, Hash) - Um Hash de estilos CSS para alterar antes de tentar anexar o arquivo, se `true` {opacity: 1, display: 'block', visibilidade: 'visible'} é usado (pode não ser suportado por todos os drivers)
*exact* - Corresponda o nome / conteúdo exato da etiqueta ou aceite uma correspondência parcial.

*:currently_with* — A propriedade de valor atual do campo para preencher

*:fill_options*— Opções específicas do driver sobre como preencher campos

*:from* — O id, nome ou rótulo da caixa de seleção

*id* - Corresponder campos que correspondem ao atributo id

*match* - A estratégia de correspondência a ser usada (:one,:first,:prefer_exact,:smart).

*multiple* - Campo de correspondência que permite a seleção de vários arquivos.

*name* - Corresponder campos que correspondem ao atributo name

*:option* (String) — Valor da caixa de seleção para selecionar

*:option* — Valor do radio_button para escolher

*:placeholder* — Corresponder campos que correspondam ao atributo de espaço reservado

*wait* - Tempo máximo para aguardar a exibição do elemento correspondente.

*:with* — O valor a preencher - obrigatório
------------------------------------------------------------------------------

## document marchter

#assert_no_title(title, **options) ⇒ true
Asserts that the page doesn't have the given title.

Parameters:

options (Hash) — a customizable set of options
Options Hash (**options):

:wait (Numeric) — default: Capybara.default_max_wait_time — Maximum time that Capybara will wait for title to eq/match given string/regexp argument
:exact (Boolean) — default: false — When passed a string should the match be exact or just substring
Returns:

(true)

#assert_title(title, **options) ⇒ true
Asserts that the page has the given title.

Parameters:

options (Hash) — a customizable set of options
Options Hash (**options):

:wait (Numeric) — default: Capybara.default_max_wait_time — Maximum time that Capybara will wait for title to eq/match given string/regexp argument
:exact (Boolean) — default: false — When passed a string should the match be exact or just substring
Returns:

(true)

#has_no_title?(title, **options) ⇒ Boolean
Checks if the page doesn't have the given title.

Parameters:

options (Hash) — a customizable set of options
Options Hash (**options):

:wait (Numeric) — default: Capybara.default_max_wait_time — Maximum time that Capybara will wait for title to eq/match given string/regexp argument
:exact (Boolean) — default: false — When passed a string should the match be exact or just substring

Returns:

(Boolean)

#has_title?(title, **options) ⇒ Boolean
Checks if the page has the given title.

Parameters:

options (Hash) — a customizable set of options
Options Hash (**options):

:wait (Numeric) — default: Capybara.default_max_wait_time — Maximum time that Capybara will wait for title to eq/match given string/regexp argument
:exact (Boolean) — default: false — When passed a string should the match be exact or just substring
----------------------------------------------------------------------------
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
----------------------------------------------------------------------------

## Finders

#all([kind = Capybara.default_selector], locator = nil, options = {}) ⇒ Capybara::Result (also: #find_all)
Find all elements on the page matching the given selector and options.

Parameters:

kind (Symbol) — Optional selector type (:css, :xpath, :field, etc.) - Defaults to Capybara.default_selector
locator (String) (defaults to: nil) — The locator for the specified selector
options (Hash) (defaults to: {}) — a customizable set of options
Options Hash (options):

text (String, Regexp) — Only find elements which contain this text or match this regexp
exact_text (String, Boolean) — default: Capybara.exact_text — When String the elements contained text must match exactly, when Boolean controls whether the :text option must match exactly
visible (Boolean, Symbol) — Only find elements with the specified visibility:
true - only finds visible elements.
false - finds invisible and visible elements.
:all - same as false; finds visible and invisible elements.
:hidden - only finds invisible elements.
:visible - same as true; only finds visible elements.
count (Integer) — Exact number of matches that are expected to be found
maximum (Integer) — Maximum number of matches that are expected to be found
minimum (Integer) — Minimum number of matches that are expected to be found
between (Range) — Number of matches found must be within the given range
exact (Boolean) — Control whether `is` expressions in the given XPath match exactly or partially
wait (Integer, false) — default: Capybara.default_max_wait_time — The time to wait for matching elements to become available
Returns:

(Capybara::Result) — A collection of found elements

#ancestor(*args, **options, &optional_filter_block) ⇒ Capybara::Node::Element
Find an Element based on the given arguments that is also an ancestor of the element called on.

Parameters:

options (Hash) — a customizable set of options
kind (Symbol) — Optional selector type (:css, :xpath, :field, etc.) - Defaults to Capybara.default_selector
locator (String) — The locator for the specified selector
options (Hash) — a customizable set of options
Options Hash (**options):

wait (false, Numeric) — default: Capybara.default_max_wait_time — Maximum time to wait for matching element to appear.
match (Boolean) — The matching strategy to use.

#find(*args, **options, &optional_filter_block) ⇒ Capybara::Node::Element
Find an Element based on the given arguments.

Parameters:

options (Hash) — a customizable set of options
kind (Symbol) — Optional selector type (:css, :xpath, :field, etc.) - Defaults to Capybara.default_selector
locator (String) — The locator for the specified selector
options (Hash) — a customizable set of options
Options Hash (**options):

wait (false, Numeric) — default: Capybara.default_max_wait_time — Maximum time to wait for matching element to appear.
match (Boolean) — The matching strategy to use.

#find_button([locator], options = {}) ⇒ Capybara::Node::Element
Find a button on the page.

Parameters:

locator (String) — id, value, title, text content, alt of image
Options Hash (options):

wait (false, Numeric) — default: Capybara.default_max_wait_time — Maximum time to wait for matching element to appear.
disabled (Boolean, Symbol) — default: false — Match disabled button?
true - only finds a disabled button
false - only finds an enabled button
:all - finds either an enabled or disabled button
id (String) — Match buttons with the id provided
title (String) — Match buttons with the title provided
value (String) — Match buttons with the value provided
class (String, Array<String>) — Match buttons that match the class(es) provided



#find_by_id(id, **options, &optional_filter_block) ⇒ Capybara::Node::Element
Find a element on the page, given its id.

Parameters:

id (String) — id of element
options (Hash) — a customizable set of options
Options Hash (**options):

wait (false, Numeric) — default: Capybara.default_max_wait_time — Maximum time to wait for matching element to appear.

#find_field([locator], options = {}) ⇒ Capybara::Node::Element
Find a form field on the page.

Parameters:

locator (String) — name, id, placeholder or text of associated label element
Options Hash (options):

wait (false, Numeric) — default: Capybara.default_max_wait_time — Maximum time to wait for matching element to appear.
checked (Boolean) — Match checked field?
unchecked (Boolean) — Match unchecked field?
disabled (Boolean, Symbol) — default: false — Match disabled field?
true - only finds a disabled field
false - only finds an enabled field
:all - finds either an enabled or disabled field
readonly (Boolean) — Match readonly field?
with (String, Regexp) — Value of field to match on
type (String) — Type of field to match on
multiple (Boolean) — Match fields that can have multiple values?
id (String) — Match fields that match the id attribute
name (String) — Match fields that match the name attribute
placeholder (String) — Match fields that match the placeholder attribute
Match (String, Array<String>) — fields that match the class(es) passed


#find_link([locator], options = {}) ⇒ Capybara::Node::Element
Find a link on the page.

Parameters:

locator (String) — id, title, text, or alt of enclosed img element
Options Hash (options):

wait (false, Numeric) — default: Capybara.default_max_wait_time — Maximum time to wait for matching element to appear.
href (String, Regexp, nil) — Value to match against the links href, if nil finds link placeholders (<a> elements with no href attribute)
id (String) — Match links with the id provided
title (String) — Match links with the title provided
alt (String) — Match links with a contained img element whose alt matches
class (String, Array<String>) — Match links that match the class(es) provided

#first([kind], locator, options) ⇒ Capybara::Node::Element
Find the first element on the page matching the given selector and options.

Parameters:

kind (:css, :xpath) — The type of selector
locator (String) — The selector
options (Hash) — Additional options; see #all

#sibling(*args, **options, &optional_filter_block) ⇒ Capybara::Node::Element
Find an Element based on the given arguments that is also a sibling of the element called on.

Parameters:

options (Hash) — a customizable set of options
kind (Symbol) — Optional selector type (:css, :xpath, :field, etc.) - Defaults to Capybara.default_selector
locator (String) — The locator for the specified selector
options (Hash) — a customizable set of options
Options Hash (**options):

wait (false, Numeric) — default: Capybara.default_max_wait_time — Maximum time to wait for matching element to appear.
match (Boolean) — The matching strategy to use.
----------------------------------------------------------------------------
## MAtcher

#assert_all_of_selectors([kind = Capybara.default_selector], *locators, options = {}) ⇒ Object
Asserts that all of the provided selectors are present on the given page or descendants of the current node.

Parameters:

kind (Symbol) — Optional selector type (:css, :xpath, :field, etc.) - Defaults to Capybara.default_selector
locator (String) — The locator for the specified selector
options (Hash) — a customizable set of options

#assert_matches_selector(*args, &optional_filter_block) ⇒ Object
Asserts that the current_node matches a given selector.
#assert_no_selector(*args, &optional_filter_block) ⇒ Object (also: #refute_selector)
Asserts that a given selector is not on the page or a descendant of the current node.
#assert_no_text(*args) ⇒ true
Asserts that the page or current node doesn't have the given text content, ignoring any HTML tags.

Parameters:

type (:all, :visible) — Whether to check for only visible or all text. If this parameter is missing or nil then we use the value of `Capybara.ignore_hidden_elements`, which defaults to `true`, corresponding to `:visible`.
text (String, Regexp) — The string/regexp to check for. If it's a string, text is expected to include it. If it's a regexp, text is expected to match it.
Options Hash (options):

:count (Integer) — default: nil — Number of times the text is expected to occur
:minimum (Integer) — default: nil — Minimum number of times the text is expected to occur
:maximum (Integer) — default: nil — Maximum number of times the text is expected to occur
:between (Range) — default: nil — Range of times that is expected to contain number of times text occurs
:wait (Numeric) — default: Capybara.default_max_wait_time — Maximum time that Capybara will wait for text to eq/match given string/regexp argument
:exact (Boolean) — default: Capybara.exact_text — Whether text must be an exact match or just substring

#assert_none_of_selectors([kind = Capybara.default_selector], *locators, options = {}) ⇒ Object
Asserts that none of the provided selectors are present on the given page or descendants of the current node.
#assert_not_matches_selector(*args, &optional_filter_block) ⇒ Object (also: #refute_matches_selector)
#assert_selector(*args, &optional_filter_block) ⇒ Object
Asserts that a given selector is on the page or a descendant of the current node.
#assert_text(*args) ⇒ true
Asserts that the page or current node has the given text content, ignoring any HTML tags.

Parameters:

type (:all, :visible) — Whether to check for only visible or all text. If this parameter is missing or nil then we use the value of `Capybara.ignore_hidden_elements`, which defaults to `true`, corresponding to `:visible`.
text (String, Regexp) — The string/regexp to check for. If it's a string, text is expected to include it. If it's a regexp, text is expected to match it.
Options Hash (options):

:count (Integer) — default: nil — Number of times the text is expected to occur
:minimum (Integer) — default: nil — Minimum number of times the text is expected to occur
:maximum (Integer) — default: nil — Maximum number of times the text is expected to occur
:between (Range) — default: nil — Range of times that is expected to contain number of times text occurs
:wait (Numeric) — default: Capybara.default_max_wait_time — Maximum time that Capybara will wait for text to eq/match given string/regexp argument
:exact (Boolean) — default: Capybara.exact_text — Whether text must be an exact match or just substring

#has_button?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a button with the given text, value or id.
#has_checked_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a radio button or checkbox with the given label, value or id, that is currently checked.
#has_css?(path, **options, &optional_filter_block) ⇒ Boolean
Checks if a given CSS selector is on the page or a descendant of the current node.

Parameters:

path (String) — A CSS selector
options (Hash) — a customizable set of options
Options Hash (**options):

:count (Integer) — default: nil — Number of times the selector should occur
Returns:

(Boolean) — If the selector exists

#has_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a form field with the given label, name or id.

Parameters:

locator (String) (defaults to: nil) — The label, name or id of a field to check for
options (Hash) — a customizable set of options
Options Hash (**options):

:with (String, Regexp) — The text content of the field or a Regexp to match
:type (String) — The type attribute of the field

#has_link?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a link with the given text or id.

Parameters:

locator (String) (defaults to: nil) — The text or id of a link to check for
options
Options Hash (**options):

:href (String, Regexp) — The value the href attribute must be

#has_no_button?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no button with the given text, value or id.
#has_no_checked_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no radio button or checkbox with the given label, value or id, that is currently checked.
#has_no_css?(path, **options, &optional_filter_block) ⇒ Boolean
Checks if a given CSS selector is not on the page or a descendant of the current node.
#has_no_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no form field with the given label, name or id.

Parameters:

locator (String) (defaults to: nil) — The label, name or id of a field to check for
options (Hash) — a customizable set of options
Options Hash (**options):

:with (String, Regexp) — The text content of the field or a Regexp to match
:type (String) — The type attribute of the field

#has_no_link?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no link with the given text or id.
#has_no_select?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no select field with the given label, name or id.
#has_no_selector?(*args, &optional_filter_block) ⇒ Boolean
Checks if a given selector is not on the page or a descendant of the current node.
#has_no_table?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no table with the given id or caption.
#has_no_text?(*args) ⇒ Boolean (also: #has_no_content?)
Checks if the page or current node does not have the given text content, ignoring any HTML tags and normalizing whitespace.
#has_no_unchecked_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has no radio button or checkbox with the given label, value or id, that is currently unchecked.
#has_no_xpath?(path, **options, &optional_filter_block) ⇒ Boolean
Checks if a given XPath expression is not on the page or a descendant of the current node.
#has_select?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a select field with the given label, name or id.

Parameters:

locator (String) (defaults to: nil) — The label, name or id of a select box
options (Hash) — a customizable set of options
Options Hash (**options):

:options (Array) — Options which should be contained in this select box
:with_options (Array) — Partial set of options which should be contained in this select box
:selected (String, Array) — Options which should be selected
:with_selected (String, Array) — Partial set of options which should minimally be selected

#has_selector?(*args, &optional_filter_block) ⇒ Boolean
Checks if a given selector is on the page or a descendant of the current node.

Parameters:

args
kind (Symbol) — Optional selector type (:css, :xpath, :field, etc.) - Defaults to Capybara.default_selector
locator (String) — The locator for the specified selector
options (Hash) — a customizable set of options
Options Hash (*args):

:count (Integer) — default: nil — Number of times the text should occur
:minimum (Integer) — default: nil — Minimum number of times the text should occur
:maximum (Integer) — default: nil — Maximum number of times the text should occur
:between (Range) — default: nil — Range of times that should contain number of times text occurs

#has_table?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a table with the given id or caption:.
#has_text?(*args) ⇒ Boolean (also: #has_content?)
Checks if the page or current node has the given text content, ignoring any HTML tags.

Parameters:

type (:all, :visible) — Whether to check for only visible or all text. If this parameter is missing or nil then we use the value of `Capybara.ignore_hidden_elements`, which defaults to `true`, corresponding to `:visible`.
text (String, Regexp) — The string/regexp to check for. If it's a string, text is expected to include it. If it's a regexp, text is expected to match it.
Options Hash (options):

:count (Integer) — default: nil — Number of times the text is expected to occur
:minimum (Integer) — default: nil — Minimum number of times the text is expected to occur
:maximum (Integer) — default: nil — Maximum number of times the text is expected to occur
:between (Range) — default: nil — Range of times that is expected to contain number of times text occurs
:wait (Numeric) — default: Capybara.default_max_wait_time — Maximum time that Capybara will wait for text to eq/match given string/regexp argument
:exact (Boolean) — default: Capybara.exact_text — Whether text must be an exact match or just substring

#has_unchecked_field?(locator = nil, **options, &optional_filter_block) ⇒ Boolean
Checks if the page or current node has a radio button or checkbox with the given label, value or id, that is currently unchecked.
#has_xpath?(path, **options, &optional_filter_block) ⇒ Boolean
Checks if a given XPath expression is on the page or a descendant of the current node.

Parameters:

path (String) — An XPath expression
options (Hash) — a customizable set of options
Options Hash (**options):

:count (Integer) — default: nil — Number of times the expression should occur

#matches_css?(css, **options, &optional_filter_block) ⇒ Boolean
Checks if the current node matches given CSS selector.
#matches_selector?(*args, &optional_filter_block) ⇒ Boolean
Checks if the current node matches given selector.
#matches_xpath?(xpath, **options, &optional_filter_block) ⇒ Boolean
Checks if the current node matches given XPath expression.
#not_matches_css?(css, **options, &optional_filter_block) ⇒ Boolean
Checks if the current node does not match given CSS selector.
#not_matches_selector?(*args, &optional_filter_block) ⇒ Boolean
Checks if the current node does not match given selector Usage is identical to Capybara::Node::Matchers#has_selector?.
#not_matches_xpath?(xpath, **options, &optional_filter_block) ⇒ Boolean
Checks if the current node does not match given XPath expression.
----------------------------------------------------------------------------
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
---------------------------------------------------------------------------

## Driver base

#accept_modal(type, **options, &blk) ⇒ String
Execute the block, and then accept the modal opened.

Parameters:

type (:alert, :confirm, :prompt)
options (Hash) — a customizable set of options
Options Hash (**options):

:wait (Numeric) — How long to wait for the modal to appear after executing the block.
:text (String, Regexp) — Text to verify is in the message shown in the modal
:with (String) — Text to fill in in the case of a prompt
Returns:

(String) — the message shown in the modal

#close_window(handle) ⇒ Object
#current_url ⇒ Object
#current_window_handle ⇒ Object
#dismiss_modal(type, **options, &blk) ⇒ String
Execute the block, and then dismiss the modal opened.

Parameters:

type (:alert, :confirm, :prompt)
options (Hash) — a customizable set of options
Options Hash (**options):

:wait (Numeric) — How long to wait for the modal to appear after executing the block.
:text (String, Regexp) — Text to verify is in the message shown in the modal
Returns:

(String) — the message shown in the modal

#evaluate_async_script(script, *args) ⇒ Object
#evaluate_script(script, *args) ⇒ Object
#execute_script(script, *args) ⇒ Object
#find_css(query) ⇒ Object
#find_xpath(query) ⇒ Object
#frame_title ⇒ Object
#frame_url ⇒ Object
#go_back ⇒ Object
#go_forward ⇒ Object
#html ⇒ Object
#invalid_element_errors ⇒ Object
#maximize_window(handle) ⇒ Object
#needs_server? ⇒ Boolean
#no_such_window_error ⇒ Object
#open_new_window ⇒ Object
#refresh ⇒ Object
#reset! ⇒ Object
#resize_window_to(handle, width, height) ⇒ Object
#response_headers ⇒ Object
#save_screenshot(path, **options) ⇒ Object
#session_options ⇒ Object
#status_code ⇒ Object
#switch_to_frame(frame) ⇒ Object
#switch_to_window(handle) ⇒ Object
#visit(path) ⇒ Object
#wait? ⇒ Boolean
#window_handles ⇒ Object
#window_size(handle) ⇒ Object
-----------------------------------------------------------------------
## rspecmatcher

#become_closed(**options) ⇒ Object
Wait for window to become closed.
#have_all_of_selectors(*args, &optional_filter_block) ⇒ Object
RSpec matcher for whether the element(s) matching a group of selectors exist See Node::Matcher#assert_all_of_selectors.
#have_button(locator = nil, **options, &optional_filter_block) ⇒ Object
RSpec matcher for buttons See Node::Matchers#has_button?.
#have_checked_field(locator = nil, **options, &optional_filter_block) ⇒ Object
RSpec matcher for checked fields See Node::Matchers#has_checked_field?.
#have_css(css, **options, &optional_filter_block) ⇒ Object
RSpec matcher for whether elements(s) matching a given css selector exist See Node::Matchers#has_css?.
#have_current_path(path, **options) ⇒ Object
RSpec matcher for the current path See SessionMatchers#assert_current_path.
#have_field(locator = nil, **options, &optional_filter_block) ⇒ Object
RSpec matcher for links See Node::Matchers#has_field?.
#have_link(locator = nil, **options, &optional_filter_block) ⇒ Object
RSpec matcher for links See Node::Matchers#has_link?.
#have_none_of_selectors(*args, &optional_filter_block) ⇒ Object
RSpec matcher for whether no element(s) matching a group of selectors exist See Node::Matcher#assert_none_of_selectors.
#have_select(locator = nil, **options, &optional_filter_block) ⇒ Object
RSpec matcher for select elements See Node::Matchers#has_select?.
#have_selector(*args, &optional_filter_block) ⇒ Object
RSpec matcher for whether the element(s) matching a given selector exist See Node::Matcher#assert_selector.
#have_table(locator = nil, **options, &optional_filter_block) ⇒ Object
RSpec matcher for table elements See Node::Matchers#has_table?.
#have_text(*args) ⇒ Object (also: #have_content)
RSpec matcher for text content See SessionMatchers#assert_text.
#have_title(title, **options) ⇒ Object
#have_unchecked_field(locator = nil, **options, &optional_filter_block) ⇒ Object
RSpec matcher for unchecked fields See Node::Matchers#has_unchecked_field?.
#have_xpath(xpath, **options, &optional_filter_block) ⇒ Object
RSpec matcher for whether elements(s) matching a given xpath selector exist See Node::Matchers#has_xpath?.
#match_css(css, **options, &optional_filter_block) ⇒ Object
RSpec matcher for whether the current element matches a given css selector.
#match_selector(*args, &optional_filter_block) ⇒ Object
RSpec matcher for whether the current element matches a given selector See Node::Matchers#assert_matches_selector.
#match_xpath(xpath, **options, &optional_filter_block) ⇒ Object
RSpec matcher for whether the current element matches a given xpath selector.
---------------------------------------------------------------------------

##session

#accept_alert(text = nil, **options, &blk) ⇒ String
Execute the block, accepting a alert.
#accept_confirm(text = nil, **options, &blk) ⇒ String
Execute the block, accepting a confirm.
#accept_prompt(text = nil, **options, &blk) ⇒ String
Execute the block, accepting a prompt, optionally responding to the prompt.
#config ⇒ Object
#configure {|config| ... } ⇒ Object
Accepts a block to set the configuration options if Capybara.threadsafe == true.
#current_host ⇒ String
Host of the current page.
#current_path ⇒ String
Path of the current page, without any domain information.
#current_scope ⇒ Object
#current_url ⇒ String
Fully qualified URL of the current page.
#current_window ⇒ Capybara::Window
Current window.
#dismiss_confirm(text = nil, **options, &blk) ⇒ String
Execute the block, dismissing a confirm.
#dismiss_prompt(text = nil, **options, &blk) ⇒ String
Execute the block, dismissing a prompt.
#document ⇒ Object
#driver ⇒ Object
#evaluate_async_script(script, *args) ⇒ Object
Evaluate the given JavaScript and obtain the result from a callback function which will be passed as the last argument to the script.
#evaluate_script(script, *args) ⇒ Object
Evaluate the given JavaScript and return the result.
#execute_script(script, *args) ⇒ Object
Execute the given script, not returning a result.
#go_back ⇒ Object
Move back a single entry in the browser's history.
#go_forward ⇒ Object
Move forward a single entry in the browser's history.
#html ⇒ String (also: #body, #source)
A snapshot of the DOM of the current document, as it looks right now (potentially modified by JavaScript).
#initialize(mode, app = nil) ⇒ Session constructor
A new instance of Session.
#inspect ⇒ Object
#open_new_window ⇒ Capybara::Window
Open new window.
#raise_server_error! ⇒ Object
Raise errors encountered in the server.
#refresh ⇒ Object
Refresh the page.
#reset! ⇒ Object (also: #cleanup!, #reset_session!)
Reset the session (i.e. remove cookies and navigate to blank page).
#response_headers ⇒ Hash{String => String}
Returns a hash of response headers.
#save_and_open_page(path = nil) ⇒ Object
Save a snapshot of the page and open it in a browser for inspection.
#save_and_open_screenshot(path = nil, **options) ⇒ Object
Save a screenshot of the page and open it for inspection.
#save_page(path = nil) ⇒ String
Save a snapshot of the page.
#save_screenshot(path = nil, **options) ⇒ String
Save a screenshot of page.
#status_code ⇒ Integer
Returns the current HTTP status code as an Integer.
#switch_to_frame(frame) ⇒ Object
Switch to the given frame.
#switch_to_window(window = nil, **options, &window_locator) ⇒ Capybara::Window
Window that has been switched to.
#using_wait_time(seconds) ⇒ Object
Yield a block using a specific wait time.
#visit(visit_uri) ⇒ Object
Navigate to the given URL.
#window_opened_by(**options, &block) ⇒ Capybara::Window
Get the window that has been opened by the passed block.
#windows ⇒ Array<Capybara::Window>
Get all opened windows.
#within(*args) ⇒ Object (also: #within_element)
Executes the given block within the context of a node.
#within_fieldset(locator) ⇒ Object
Execute the given block within the a specific fieldset given the id or legend of that fieldset.
#within_frame(*args) ⇒ Object
Execute the given block within the given iframe using given frame, frame name/id or index.
#within_table(locator) ⇒ Object
Execute the given block within the a specific table given the id or caption of that table.
#within_window(window_or_proc) ⇒ Object
This method does the following:.