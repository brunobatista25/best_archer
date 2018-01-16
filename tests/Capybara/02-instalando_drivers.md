# Instalando os Drivers

# Chromedriver

O ChromeDriver é um servidor autônomo que implementa o protocolo de fio da WebDriver para o Chromium, que está disponível para o Chrome no Android e no Chrome na área de trabalho (Mac, Linux, Windows e ChromeOS)

# Instalando ChromeDriver e GeckoDriver no Windows 

Uma dica para instalar no windows de forma global e usando o npm:

Então vamos lá:

a) Primeiramente vamos instalar a versão LTS do Nodejs, no site https://nodejs.org/en/

b) Abra o terminal e digite o seguinte comando: 

```
node –v
```

c) Em seguida, digite

```
npm –v
```

Se tudo ocorreu bem você deve ver a versão do node e npm instalados no seu computador

Agora abra o Console do Cmder ou terminal como Administrador

Para instalar o Geckodriver, digite o comando 

```
npm install -g geckodriver
```

Para instalar o Chromedriver, digite o comando 

```
npm install -g chromedriver
```

# GeckoDriver

Gecko Driver é a conexão entre seus testes em Selenium e o programa Firefox. Clientes compatíveis para interagir com navegadores baseados em Gecko, ou seja, Mozilla Firefox para esta situação.

# Instalando ChromeDriver e GeckoDriver no Mac:

A instalação no mac e bem simples bastar usar o homebrew e usar o seguinte comando: 

Para instalar o chromedriver basta digitar no terminal

```
brew install chromedriver
```

Para instalar o geckodriver basta digitar no terminal

```
brew install geckodriver
```

# Instalando ChromeDriver e GeckoDriver no Linux:

Para instalar o chrome driver e geckodriver no linux pode se usar o mesmo passo da instalação do windows então basta instalar o npm e depois usar os seguintes comandos:

Para instalar o Geckodriver, digite o comando 

```
npm install -g geckodriver
```

Para instalar o Chromedriver, digite o comando 

```
npm install -g chromedriver
```

Vamos para o próximo post [Configuração](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/03-configurando_projeto.md);

# REFERÊNCIAS:

https://github.com/teamcapybara/capybara