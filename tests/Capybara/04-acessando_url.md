# Navegação

## Visit
Você pode usar o método de "visit" para navegar para outras páginas:
O método de visit só aceita um único parâmetro, o método de solicitação é sempre GET.

```
visit('https://www.site.com.br')
```

## Have_current_path

Você pode obter o caminho atual da sessão de navegação e testá-lo usando o have_current_path correspondente:

```ruby
expect(page).to have_current_path('https://www.site.com.br', url: true)
```

Nota : Você também pode declarar o caminho atual testando o valor "current_path" diretamente. No entanto, usar o have_current_path matcher é mais seguro, pois ele usa o comportamento de espera do Capybara para garantir que as ações anteriores (como a click_link) tenham sido concluídas.
