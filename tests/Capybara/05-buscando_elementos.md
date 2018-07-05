# Buscando Elementos

Você também pode encontrar elementos específicos, a fim de manipulá-los:

## all([kind = Capybara.default_selector], locator = nil, options = {}) 

Encontre todos os elementos na página que correspondem ao seletor e opções fornecidos.


```ruby
page.all(:css, 'elemento')
```

## Opçōes para auxiliar o all

text - Apenas encontre elementos que contenham este texto ou correspondam a este regexp


exact_text - Quando String, o texto contido no elemento deve corresponder exatamente, quando o Boolean controla se a opção: text deve corresponder exatamente

visible - Apenas encontre elementos com a visibilidade especificada:

true - só encontra elementos visíveis.

false - encontra elementos invisíveis e visíveis.

:all - mesmo que falso; encontra elementos visíveis e invisíveis.

:hidden - só encontra elementos invisíveis.

:visible - o mesmo que true; só encontra elementos visíveis.

count - Número exato de correspondências que se espera encontrar

maximum - Número máximo de correspondências que se espera encontrar

minimum - Número mínimo de correspondências que se espera encontrar

between - O número de correspondências encontradas deve estar dentro do intervalo determinado

exact - Controlar se as expressões `is` no determinado XPath correspondem exatamente ou parcialmente

wait - O tempo de espera para que elementos correspondentes fiquem disponíveis

## ancestor(*args, **options, &optional_filter_block)

Encontre um elemento com base nos argumentos fornecidos que também é um ancestral do elemento chamado.

```ruby
element.ancestor('#foo').find('.bar')
```

## Opçōes para auxiliar o ancestor

options - um conjunto personalizável de opções

kind - Tipo de seletor opcional

locator - O localizador do seletor especificado

options - um conjunto personalizável de opções


## find(*args, **options, &optional_filter_block)

Encontre um elemento com base nos argumentos fornecidos.

```ruby
find('elemento')
```

## Opçōes para auxiliar o find

wait - Tempo máximo para aguardar a exibição do elemento correspondente.

match - A estratégia de correspondência a ser usada.

# find_button([locator], options = {})

Encontre um botão na página.

```ruby
find_button('elemento_do_botao')
```

## Opçōes para auxiliar o find_button

wait - Tempo máximo para aguardar a exibição do elemento correspondente.

disabled - Corresponder botão desativado?

true - só encontra um botão desativado

false - só encontra um botão ativado

:all - encontra um botão ativado ou desativado

id  - Botões de correspondência com o id fornecido

title - Combinar botões com o título fornecido

value - Corresponder botões com o valor fornecido

class - Botões de correspondência que correspondem à (s) classe (s) fornecida (s)

## find_by_id(id, **options, &optional_filter_block)

Encontre um elemento na página, dado seu id.

```ruby
find_by_id('id_do_elemento')
```

## Opçōes para auxiliar o find_by_id

wait - Tempo máximo para aguardar a exibição do elemento correspondente.

## find_field([locator], options = {})

Encontre um campo de formulário na página.

```ruby
find_field('elemento')
```

## Opçōes para auxiliar o find_field

wait - Tempo máximo para aguardar a exibição do elemento correspondente.

checked - Corresponder campo verificado?

unchecked - Corresponder campo desmarcado?

disabled - padrão: false - Corresponder campo desativado?

true - só encontra um campo desativado

false - só encontra um campo ativado

:all - encontra um campo ativado ou desativado

readonly - Corresponder campo readonly?

with - Valor do campo para combinar

type - Tipo de campo para combinar

multiple - Corresponder campos que podem ter vários valores?

id - Corresponder campos que correspondem ao atributo id

name - Corresponder campos que correspondem ao atributo name

placeholder - Corresponder campos que correspondam ao atributo de espaço reservado

Match - campos que correspondem à (s) classe (s) passada (s)


## find_link([locator], options = {})

Encontre um link na página.

```ruby
find_link('link_do_elemento')
```

## Opçōes para auxiliar o find_link

wait - Tempo máximo para aguardar a exibição do elemento correspondente.

href - Valor para combinar com os links href, se nil encontrar espaços reservados para links (<a> elementos sem atributo href)
  
id - Corresponder links com o ID fornecido

title - Corresponder links com o título fornecido

alt - Corresponder links com um elemento img contido, cujo alt corresponde

class - Corresponder links que correspondam à (s) classe (s) fornecida (s)


## first([kind], locator, options)

Encontre o primeiro elemento na página que corresponda ao seletor e opções fornecidos.

```ruby
first('elemento')
```

## sibling(*args, **options, &optional_filter_block)

Encontre um elemento baseado nos argumentos dados que também é um irmão do elemento chamado.

```ruby
element.sibling('elemento')
```

## Opçōes para auxiliar o sibling

wait - Tempo máximo para aguardar a exibição do elemento correspondente.

match - A estratégia de correspondência a ser usada.
