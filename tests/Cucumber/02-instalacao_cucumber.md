Instalação do Cucumber

Instalar o cucumber e bem simples,bata abrir o terminal e digitar o seguinte comando:

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

Eu tambem adiciono a pasta 

```
features/specs
```
Onde nela colocamos os arquivos .feature