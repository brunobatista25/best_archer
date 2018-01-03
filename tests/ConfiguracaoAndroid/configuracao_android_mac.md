Configuração no OSX

No OSX (Mac), a instalação é semelhante a que fizemos para o Windows. Primeiramente, baixe a JDK do site da Oracle. A instalação deve ocorrer sem maiores problemas, bastando seguir o wizard com o passo a passo da instalação.

Em seguida, baixe o Android Studio. A partir do arquivo .dmg, a instalação é tranquila, seguindo o padrão para outros aplicativos do Mac. Ao executar pela primeira vez, as ferramentas serão baixadas e o HAXM será instalado.

O último passo é a configuração das variáveis de ambiente. Contando que os caminhos padrão tanto do Java quanto da SDK do Android não foram alterados durante a instalação, adicione o seguinte conteúdo ao arquivo ~/.bash_profile (caso o arquivo não exista, crie-o).

```ruby
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_111.jdk/Contents/Home
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$JAVA_HOME/bin:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
```

Por último, opcionalmente mas fortemente recomendado, instale o Git (opte por utilizar o Homebrew, para instalar a versão mais recente).

REFERÊNCIAS:

http://www.rafaeltoledo.net/configurando-o-ambiente-de-desenvolvimento-tutorial-android-1/