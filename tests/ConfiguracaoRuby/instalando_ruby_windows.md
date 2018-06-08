# Instalando Ruby e DevKit no Windows

## 1. CMD ou PowerShell?

O fato é que vamos usar muita linha de comando, e como estamos no windows temos o CMD ou PowerShell, mas qual usar?

Vamos usar o CMD mesmo, porem temos um "programinha" bem chique que da uma bela turbinada nele. o CMDER (Console Emutator). Com ele temos no Windows muitos comandos do linux e um Console bem agradável para trabalhar com linha de comando que inclusive funciona o Control C e Control V (isso é realmente bom). Até o editor de texto VIM vem junto no pacote de instalação full. Legal né?

## Segue abaixo os passos para instalação.

1) Faça download do pacote FULL no site http://cmder.net/

2) Descompactar na pasta C:\tools\Cmder (tem que criar a pasta)

3) Executar o cmder.exe (cria um atalho e coloca onde tu quiser pra ficar mais pratico)

## 2. Instalando Ruby 64 Bits
a) Fazer download da versão 2.4.2 x64 http://rubyinstaller.org/downloads/

b) Instalar no diretório C:\Ruby24-x64

c) Antes de clicar em Install marca todas as opções.

c) Feche o Console do CMDER, e abre de novo, em seguida, digite o comando ruby –v, se der tudo certo você vai ver o seguinte resultado:

```ruby
ruby 2.4.2
```
