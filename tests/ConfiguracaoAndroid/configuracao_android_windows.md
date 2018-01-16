# Configuração no Windows

O primeiro passo para a instalação do ambiente no Windows, é o download da JDK (Java Development Kit). Ela nos fornecerá a base de ferramentas para o desenvolvimento Java, que será utilizada também para o desenvolvimento dos apps Android também. Você pode baixar a JDK no site da Oracle. A instalação deve ocorrer sem problemas.

O próximo passo consiste em baixarmos o Android Studio. Após baixar o .exe bundle (que já contém os itens básicos de SDK e emulador), basta seguir o procedimento de instalação normalmente como qualquer outro aplicativo.


O último passo é exportarmos as variáveis de ambiente JAVA_HOME e ANDROID_HOME, para que possamos, quando necessário, também executar builds e comandos a partir do console. Primeiramente vamos exportar a ANDROID_HOME. Caso você não tenha alterado o local durante a instalação do Android Studio, o valor deve ser:

```ruby
%LOCALAPPDATA%\Android\sdk
```
Em seguida, vamos exportar a JAVA_HOME. Novamente, se você não alterou o local da instalação do Java, o valor deve ser:

```ruby
%ProgramFiles%\Java\jdk1.8.0_111
```

No momento que escrevo este post, a última versão do Java é a 8, revisão 111. Caso a versão que você instale seja outra, ajuste o caminho de acordo.

Por fim, vamos adicionar os binários ao Path do sistema, para que sejam acessíveis através do console. Adicione ao Path as entradas 

```ruby
%ANDROID_HOME%\tools, %ANDROID_HOME%\platform-tools e %JAVA_HOME%\bin.
```

Para testar, valide que os comandos adb e javac são acessíveis no console.

Durante a instalação do Android Studio, também deve ter sido instalado o HAXM (caso o seu processador seja compatível). O HAXM permitirá que vocẽ execute o emulador do Android com excelente desempenho. Outra boa opção de emulador é o Genymotion, porém para usos gerais, o emulador que acompanha a SDK do Android é suficiente.

Por fim, opcional mas recomendado, instale o Git, que é hoje a ferramenta de versão mais utilizada.

## REFERÊNCIAS:

http://www.rafaeltoledo.net/configurando-o-ambiente-de-desenvolvimento-tutorial-android-1/