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

## current_url
URL totalmente qualificado da página atual.

```ruby
url = page.current_url
puts url
```

**Vamos para o próximo post** [Buscando elementos](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/05-buscando_elementos.md);
