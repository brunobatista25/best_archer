#Instalação do Cucumber

Instalar o cucumber e bem simples, basta abrir o terminal e digitar o seguinte comando:

```
gem install cucumber
```

Depois de instalado para criar um projeto em cucumber basta digitar o seguinte comando em qual pasta voçê deseja que o projeto seja criado:

```
cucumber --init
``` 

Esse comando irá criar criar uma estrutura básica

```
create   features
create   features/step_definitions
create   features/support
create   features/support/env.rb
```

Onde a pasta step... é onde colocamos os arquivos .rb

Onde a pasta suport é onde fazemos nossas configurações

Eu também adiciono a pasta 

```
features/specs
```
Onde nela colocamos os arquivos .feature

Vamos paro proximo post [Comandos Given When Then And But](https://github.com/brunobatista25/best_archer/blob/master/tests/Cucumber/03-given_when_then_but_and.md);

#Referências:
	
https://github.com/cucumber/cucumber