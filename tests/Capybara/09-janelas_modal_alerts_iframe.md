## Janelas,Modal,Alerts e Iframe
-----------------------------------------------------------------------------------------

## Janela

## close_window

Método para fechar a janela do navegador

```ruby
close_window
```

## current_window

Janela corrente.

```ruby
page.current_window.resize_to(x, y)
```

## maximize_window

Método para maximizar a janela.

```ruby
page.current_window.maximize_window
```

## open_new_window 

Método para abrir uma janela.

```ruby
@session.open_new_window
```

## refresh 

Método para dar um refresh na tela.

```ruby
page.driver.browser.navigate.refresh
```

## go_back 

Retroceda uma única entrada no histórico do navegador.

```ruby
page.go_back
```

## go_forward 

Avançar uma única entrada no histórico do navegador.

```ruby
page.go_forward
```

## resize_window_to

Método para abrir uma ajustar o tamanho da tela desejada.

```ruby
page.current_window.resize_window_to(x, y)
```

## window_size

Método para abrir uma ajustar o tamanho da tela desejada.

```ruby
page.current_window.window_size(x, y)
```

## window_opened_by

Obter a janela que foi aberta pelo bloco passado.

```ruby
  janela = window_opened_by do
    click_link 'Clique aqui'
  end
```

## windows 

Pega todas as janelas abertas

```ruby
page.windows
```

## switch_to_window

Janela que foi para escolhida.

```ruby
  switch_to_window windows.last
```

## within_window

Bloco utilizado para fazer ações em determinada janela.

```ruby
  janela = window_opened_by do
    click_link 'Clique aqui'
  end

  within_window janela do

    expect(current_url).to eq 'https://automacaocombatista.herokuapp.com/mudancadefoco/newwindow'
    @mensagem = find('.red-text.text-darken-1.center')
    expect(@mensagem.text).to eq 'Você Abriu uma nova janela!!'
    janela.close
end
``` 

## window_handles

Método para pegar as janelas abertas existentes

```ruby
window_before = driver.window_handles[0]
window_after = driver.window_handles[1]
driver.switch_to_window(window_after)
```

------------------------------------------------------------------------------

## Modal

## within
Executa o bloco especificado dentro do contexto de um nó.

```ruby
within('div#delivery-address') do
  fill_in('Street', with: '12 Main Street')
end
```

## accept_modal

Execute o bloco e aceite o modal aberto.

```ruby
page.accept_modal
```

## dismiss_modal

Execute o bloco e, em seguida, descarte o modal aberto.

```ruby
page.dismiss_modal
```

------------------------------------------------------------------------------
## Iframe

## within_frame

Execute o bloco especificado dentro do iframe fornecido usando o quadro, o nome / id ou o índice do quadro.

```ruby
within_frame 'random' do
  expect(page).to have_content 'content'
end
```

------------------------------------------------------------------------------
## Alerts

## accept_alert

Execute o bloco, aceitando um alerta.

```ruby
page.accept_alert
```

## accept_confirm

Executa o bloco, aceitando a confirmação.

```ruby
page.accept_confirm
```

## accept_prompt

Executa o bloco, aceitando a confirmação, opcionalmente respondendo ao prompt.


```ruby
page.accept_prompt(with: 'bruno batista')
```

## dismiss_confirm

Executa o bloco, aceitando a confirmação.

```ruby
page.dismiss_confirm
```

## dismiss_prompt

Execute o bloco, dispensando um prompt

```ruby
page.dismiss_prompt
```

------------------------------------------------------------------------------

## Outros

## within_fieldset

Execute o bloco dado dentro de um determinado fieldset dado o id ou legenda daquele fieldset.

```ruby
within_fieldset 'random' do
  expect(page).to have_content 'content'
end
```

## within_table

Execute o bloco dado dentro de uma tabela específica, dado o id ou legenda dessa tabela.

```ruby
within_table 'random' do
  expect(page).to have_content 'content'
end
```

**Vamos para o próximo post** [Métodos de screenchots](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/10-metodos_screenshots.md);