# Comandos JavaScript

## evaluate_async_script
Avalie o JavaScript fornecido e obtenha o resultado de uma função de retorno de chamada que será passada como o último argumento para o script.

```ruby
page.evaluate_async_script('script')
```

## evaluate_script
Avalie o JavaScript fornecido e retorne o resultado.


```ruby
page.evaluate_script('script')
```

## execute_script
Execute o script fornecido, não retornando um resultado.

```ruby
page.execute_script('script')
```

## trigger
Acione qualquer evento no elemento atual, por exemplo, eventos de mouseover ou foco.

```ruby
page.find('element_name').trigger(:mouseover)  
```

**Vamos para o próximo post** [Comandos Web responsiva com Capybara](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/12-web_responsiva_capybara.md);
