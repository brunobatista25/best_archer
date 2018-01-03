Configuração no Linux

No Linux, por possuirmos um gerenciador de pacotes, a coisa fica um pouco mais fácil. Caso você esteja utilizando o Ubuntu / Linux Mint, para preparar nosso ambiente, basta instalar os seguintes pacotes:

```ruby
sudo apt-get install lib32z1 lib32ncurses5 lib32stdc++6 openjdk-8-jdk qemu-kvm libvirt-bin ubuntu-vm-builder bridge-utils
```
Caso esteja utilizando o Fedora, os pacotes são:

```ruby
sudo dnf install glibc.i686 glibc-devel.i686 libstdc++.i686 zlib-devel.i686 ncurses-devel.i686 libX11-devel.i686 libXrender.i686 libXrandr.i686 java-1.8.0-openjdk-devel qemu-kvm
```

Outras distribuições podem ter estes pacotes com outros nomes, mas uma rápida busca pode trazer os correspondentes. O Linux não utiliza o HAXM para aceleração dos emuladores x86 – para isso, temos o KVM, um mecanismo de virtualização ligado ao kernel (caso o seu processador suporte).

Em seguida, vamos baixar o Android Studio. Para Linux, o arquivo tem extensão .tar.gz e deve ser extraído para alguma pasta (como por exemplo, ~/Android). Feito isso, basta executar o arquivo studio.sh que encontra-se dentro da pasta bin. Na primeira execução, serão baixados os pacotes necessários para a SDK. Para encerrar, selecione no menu Configure a opção Create Desktop Entry para facilitar a execução do Android Studio a partir do seu menu de aplicativos (seja Unity, Gnome, KDE, etc.)

O último passo é exportarmos a variável ANDROID_HOME e colocar os binários no Path. Para isso abra o arquivo ~/.bashrc ou, caso esteja utilizando o zshell, ~/.zshrc, e adicione as seguintes linhas. Caso tenha modificado o local da instalação da SDK do Android, ajuste o caminho:

```ruby
export ANDROID_HOME="$HOME/Android/Sdk"
export PATH="$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools"
```

Por fim, é opcional porém recomendada, a instalação do Git para controle de versão dos nossos projetos.

REFERÊNCIAS:

http://www.rafaeltoledo.net/configurando-o-ambiente-de-desenvolvimento-tutorial-android-1/