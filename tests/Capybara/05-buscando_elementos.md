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


**:all** - encontra um campo ativado ou desativado

**alt** - Corresponder links com um elemento img contido, cujo alt corresponde

**between** - O número de correspondências encontradas deve estar dentro do intervalo determinado

**checked** - Corresponder campo verificado?

**class** - Corresponder links que correspondam à (s) classe (s) fornecida (s)

**count** - Número exato de correspondências que se espera encontrar

**disabled** - padrão: false - Corresponder campo desativado?

**exact** - Controlar se as expressões `is` no determinado XPath correspondem exatamente ou parcialmente

**exact_text** - Quando String, o texto contido no elemento deve corresponder exatamente, quando o Boolean controla se a opção: text deve corresponder exatamente

**false** - só encontra um campo ativado

**:hidden** - só encontra elementos invisíveis.

**href** - Valor para combinar com os links href, se nil encontrar espaços reservados para links (<a> elementos sem atributo href)

**id** - Corresponder links com o ID fornecido

**match** - A estratégia de correspondência a ser usada.

**maximum** - Número máximo de correspondências que se espera encontrar

**minimum** - Número mínimo de correspondências que se espera encontrar

**multiple** - Corresponder campos que podem ter vários valores?

**name** - Corresponder campos que correspondem ao atributo name

**placeholder** - Corresponder campos que correspondam ao atributo de espaço reservado

**readonly** - Corresponder campo readonly?

**text** - Apenas encontre elementos que contenham este texto ou correspondam a este regexp

**title** - Corresponder links com o título fornecido

**true** - só encontra um campo desativado

**type** - Tipo de campo para combinar

**unchecked** - Corresponder campo desmarcado?

**value** - Corresponder botões com o valor fornecido

**visible** - Apenas encontre elementos com a visibilidade especificada:

**:visible** - o mesmo que true; só encontra elementos visíveis.

**wait** - Tempo máximo para aguardar a exibição do elemento correspondente.

**with** - Valor do campo para combinar

**Vamos para o próximo post** [Reaizando açōes](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/06-realizando_acoes.md);