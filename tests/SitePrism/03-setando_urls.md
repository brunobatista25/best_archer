# Setando urls

Uma página geralmente tem um URL. Se você quiser navegar até uma página, precisará definir seu URL. Veja como:

```ruby
class Home < SitePrism::Page
  set_url 'http://www.google.com'
end
```

Se você tiver definido o app_host de Capybara, poderá definir o URL da seguinte maneira:

```ruby
class Home < SitePrism::Page
  set_url '/home.htm'
end
```

Tenha em atenção que a definição de um URL é opcional. Basta definir um URL para poder navegar diretamente para essa página. Faz sentido definir o URL para um modelo de página de uma página inicial ou uma página de login, mas provavelmente não é uma página de resultados de pesquisa.
