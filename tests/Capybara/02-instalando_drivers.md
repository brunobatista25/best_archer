
# Instalando os Drivers

## Chromedriver

O ChromeDriver é um servidor autônomo que implementa o protocolo de fio da WebDriver para o Chromium, que está disponível para o Chrome no Android e no Chrome na área de trabalho (Mac, Linux, Windows e ChromeOS)
> Download: https://bit.ly/2e6e5sz

## GeckoDriver

Gecko Driver é a conexão entre seus testes em Selenium e o programa Firefox. Clientes compatíveis para interagir com navegadores baseados em Gecko, ou seja, Mozilla Firefox para esta situação.
> Download: https://bit.ly/2joYOJD

## PhantomJS

PhantomJS é basicamente um browser sem interface gráfica baseado no WebKit (similar ao Safari e Google Chrome), onde você roda em background e manipula via API JavaScript. A vantagem de usar o PhantomJS é que ele é compátivel com qualquer sistema de poder ser instalado em qualquer máquina.
> Download: https://bit.ly/2re71RE

## Instalando ChromeDriver, GeckoDriver e PhantomJS no Windows 

> Temos duas opções de instalação dos drivers

**Instalação manual**

  1. Baixe os respectivos drivers nos links de download logo acima.
  2. Se necessário, extraia o arquivo .exe para alguma pasta do seu desktop.
  3. Coloque os executáveis dentro da pasta **C:\Windows** e *voilà*
  
**Instalação via NPM** 

  1. Baixe o NodeJs no site https://bit.ly/1LjG5AH e execute a instalação
  2. Para verificar se a instalação foi um sucesso, abra o PowerShell ou CMDER e digite os seguintes comandos:
	`node -v` 
    `npm -v`
		>Você deve receber de retorno as versões das ferramentas.
  4. Com o PowerShell ou CMDER aberto, para instalar o GeckoDriver, o ChromeDriver e o PhantomJS, digite:
	 > GeckoDriver
    `npm install -g geckodriver `
    
	 > ChromeDriver
    `npm install -g chromedriver`
    
   > PhantomJS
    `npm install -g phantomjs-prebuilt`


## Instalando ChromeDriver, GeckoDriver e PhamtomJS no Mac:

A instalação no MacOS, assim como no Linux, é ainda mais fácil.

1. Abra o terminal e instale o HomeBrew com o comando:
	```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```

2. Para verificar se o HomeBrew foi instalado corretamente, digite **which brew**. Você deverá ver algo como:
	>**/usr/local/bin/brew**
	
3. Para instalar o GeckoDriver, o ChromeDriver e o PhantomJs, digite:
	 > GeckoDriver
    `brew install geckodriver `
    
	 > ChromeDriver
    `brew install chromedriver`
    
  	 > PhantomJS
    `brew install phantomjs`

## Instalando ChromeDriver, GeckoDriver e PhantomJS no Linux:

Para instalar os drivers no Linux, podemos usar o mesmo método do NPM. Apenas uma observação que o Linux possui algumas particuladores na hora de instalar o Node. Basta seguir este guia https://bit.ly/2HD54sW que vai dar tudo certo! 
  1. Com o Terminal aberto, para instalar o GeckoDriver, o ChromeDriver e o PhantomJS, digite:
	 > GeckoDriver
    `npm install -g geckodriver `
    
	 > ChromeDriver
    `npm install -g chromedriver`
    
  	 > PhantomJS
    `npm install -g phantomjs-prebuilt`
    


Vamos para o próximo post [Configuração](https://github.com/brunobatista25/best_archer/blob/master/tests/Capybara/03-configurando_projeto.md);

## REFERÊNCIAS:

https://github.com/teamcapybara/capybara

http://phantomjs.org/download.html

https://brew.sh/index_pt-br
