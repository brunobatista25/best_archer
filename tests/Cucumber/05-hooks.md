#Hooks(Ganchos)

Cucumber fornece uma série de hooks que nos permitem executar blocos em vários pontos no ciclo de teste de cucumber. Você pode colocá-los no seu support/env.rb arquivo ou em qualquer outro arquivo no support diretório, por exemplo, em um arquivo chamado support/hooks.rb. Não há associação entre onde o hooks é definido e qual cenário / passo é executado, mas você pode usar hooks marcados (veja abaixo) se você quiser mais controle de grão fino.

Todos os hooks definidos são executados sempre que ocorre o evento relevante.

#Scenario hooks(Ganchos de cenário)

#Before(Antes)

Os hooks serão executados antes do primeiro passo de cada cenário. Eles serão executados na mesma ordem em que estão registrados.

```
Before do 
  # Faça algo antes de cada cenário. 
end
```

```
Before do |cenário|
  # O argumento + argumento + é opcional, mas se você usá-lo, você pode obter o título, 
  a descrição ou o nome (título + descrição) do cenário que está prestes a ser 
  executado # . 
  Rails.logger.debug "Starting scenario: #{scenario.title}"
end
```

#After(Depois)

Os hooks serão executados após o último passo de cada cenário, mesmo quando houver etapas falhas, indefinidas, pendentes ou ignoradas. Eles correrão na ordem oposta da qual eles estão registrados.

```
After do |cenário|
  # Faça algo depois de cada cenário. 
  # O argumento + argumento + é opcional, mas 
  # se você usá-lo, você pode verificar o status com 
  # o #failed ?, #passed? e # métodos de exceção. 

  if scenario.failed?
    subject = "[Project X] #{scenario.exception.message}"
    send_failure_email(subject)
  end
end
```

Aqui é outro exemplo, onde nós saímos no primeiro fracasso (pode ser útil em alguns casos raros como Integração Contínua quando o feedback rápido é importante).

```
After do |s| 
  # Diga ao Pepino para sair depois que este cenário for concluído - se ele falhar. 
  Cucumber.wants_to_quit = true if s.failed?
end
```

#Around(Em torno)

Os hooks correrão "em torno" de um cenário. Isso pode ser usado para envolver a execução de um cenário em um bloco. O gancho Around ganha um objeto de cenário e um objeto de bloco (Proc). O cenário será executado quando você invoca block. call.

O exemplo a seguir causará que os cenários marcados com @fast falha se a execução demorar mais de 0,5 segundos:

```
Around('@fast') do |cenario, block|
  Timeout.timeout(0.5) do
    block.call
  end
end
```

Você pode querer dar uma olhada no SystemTimer se desejar mais confiável timeout.

#Step hooks(Gancho de passo)

Aviso: O bloqueio AfterStep não funciona com cenários que tenham backgrounds (cucumber 0.3.11)

```
AfterStep do |scenario|
 # Faça algo depois de cada passo. 
end
```

#Tagged hooks(Ganchos marcados)

Às vezes, você pode querer que um determinado hooks seja executado apenas para determinados cenários. Isto pode ser conseguido através da associação a Before, After, Aroundou AfterStep hooks com uma ou mais tag . Você pode tag OR e AND do mesmo modo que você pode ao executar Cucumber a partir da linha de comando. 
Exemplos:

Para tags OR, passe as tags em uma única seqüência separada por vírgulas:

```
Before('@cucumis, @sativus') do
   # Isso só será executado antes dos cenários marcados 
  # com @cucumis OR @sativus. 
end
```

Para tags AND, passe as tags como seqüências de tags separadas:

```
Before('@cucumis', '~@sativus') do
  # Isso só será executado antes dos cenários marcados 
  # com @cucumis E NÃO @sativus. 
end
```

Você cria condições de etiqueta complexas usando as tags OR e AND em:

```
Before('@cucumis, @sativus', '@aqua') do
   # Isso só será executado antes dos cenários marcados 
  # com (@cucumis OU @sativus) E @aqua  
end
```

Exemplo após passo:

```
AfterStep('@cucumis', '@sativus') do
    # Isso só será executado após as etapas dentro de cenários marcados 
  # com @cucumis AND @sativus. 
end
```

Pense duas vezes antes de usar esse recurso, pois o que quer que aconteça nos hooks é invisível para as pessoas que apenas lêem os recursos. Você deve considerar usar o plano de fundo como uma alternativa mais explícita se a configuração for legível por pessoas não-técnicas.

#Global hooks(Ganchos globais)

Se você quiser que algo aconteça uma vez antes de qualquer cenário é executado - basta colocar esse código no nível superior em seu env.rb arquivo (ou qualquer outro arquivo em seu features/support diretório. Use Kernel#at_exit para o desmontagem global. Exemplo:

```
my_heavy_object = HeavyObject.new
my_heavy_object.do_it

at_exit do
  my_heavy_object.undo_it
end
```

Running a Before hook only once (Executando um gancho antes apenas uma vez)

Se você tiver um hooks, você só deseja executar uma vez, use uma variável global:

```
Before do 
  $dunit ||= false  # tem que definir uma variável antes que possamos fazer referência ao seu its value
  return $dunit if $dunit                  # bail se $ dunit TRUE 
  step "run the really slow log in method" # caso contrário, faça isso. 
  $dunit = true                            # não faça isso novamente. 
end 
```

#AfterConfiguration(Após configuração)

Você também pode fornecer um AfterConfigurationgancho que será executado após o Cucumber ter sido configurado. O bloco que você fornecerá será passado a configuração do cucumber (uma instância de Cucumber::Cli::Configuration). Exemplo:

```
AfterConfiguration do |config|
  puts "Features dwell in #{config.feature_dirs}"
end
```

Este hooks será executado apenas uma vez; após o suporte ter sido carregado, mas antes que os recursos sejam carregados. Você pode usar esse hooks para estender o Cucumber, por exemplo, você pode afetar a forma como os recursos são carregados ou registrar formatadores personalizados programaticamente.

Vamos para o próximo post [Chamando steps dentro de step definitions](https://github.com/brunobatista25/best_archer/blob/master/tests/Cucumber/06-chamando_steps.md); 

#Referências:
	
https://github.com/cucumber/cucumber

