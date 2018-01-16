# Instalando Ruby e DevKit no Windows

## 1. CMD ou PowerShell?

O fato é que vamos usar muita linha de comando, e como estamos no windows temos o CMD ou PowerShell, mas qual usar?

Vamos usar o CMD mesmo, porem temos um "programinha" bem chique que da uma bela turbinada nele. o CMDER (Console Emutator). Com ele temos no Windows muitos comandos do linux e um Console bem agradável para trabalhar com linha de comando que inclusive funciona o Control C e Control V (isso é realmente bom). Até o editor de texto VIM vem junto no pacote de instalação full. Legal né?

## Segue abaixo os passos para instalação.

1) Faça download do pacote FULL no site http://cmder.net/

2) Descompactar na pasta C:\tools\Cmder (tem que criar a pasta neh)

3) Executar o cmder.exe (cria um atalho e coloca onde tu quiser pra ficar mais pratico)

## 2. Instalando Ruby 64 Bits
a) Fazer download da versão 2.4.2 x64 http://rubyinstaller.org/downloads/

b) Instalar no diretório C:\Ruby24-x64

c) Antes de clicar em Install marca todas as opções.

c) Feche o Console do CMDER, e abre de novo, em seguida, digite o comando ruby –v, se der tudo certo você vai ver o seguinte resultado:

```ruby
ruby 2.4.1p112
```

## 3. Instalando Devkit 64 Bits
a) http://dl.bintray.com/oneclick/rubyinstaller/DevKit-mingw64-64-4.7.2-20130224-1432-sfx.exe

b) Descompactar no diretório C:\Ruby24-x64\devkit

c) No Console do Cmder, acessar via linha de comando, a pasta onde foi instalado o DEVKIT. Com o comando:

```ruby
cd C:\Ruby24-x64\devkit
```

BREVE PAUSA: Como acesso uma pasta via linha de comando?
Imagine que você precise acessar a pasta Windows que fica no C:\.
Para isso execute o comando:

```ruby
cd c:\Windows
```
***** Fácil né? ***** \o/

d) Na sequencia digite o comando:

```ruby
ruby dk.rb init
```

e) Agora abra o arquivo config.yml que foi gerado

f) A ultima linha do arquivo deve conter o valor : -C:/Ruby24-x64. Caso contrário faça o ajuste no arquivo. Não esqueça do caractere - antes do C:\.

g) No Console do Cmder, digite o comando:

```ruby
ruby dk.rb install
```

h) Tudo deve ocorrer bem, caso contrário repita a operação desde o Passo C.


## REFERÊNCIAS:

https://medium.com/@papito/instalando-ruby-cucumber-e-capybara-no-windows-10-acb1fe833a95