# Instalando-React-Native

## Para configurar o ambiente no Linux, vamos precisar instalar 2 dependências: Node e JDK.

### Instalando CURL
Certifique-se que você tenha o CURL instalado executando o seguinte comando no terminal:

**sudo apt-get install curl**

### Instalando NodeJS
Agora com o CURL instalado, vamos instalar no NodeJS utilizando os seguintes comandos:

**curl -sL https://deb.nodesource.com/setup_10.x | sudo bash -**

**sudo apt install nodejs**
Caso você não esteja em distribuições Debian/Ubuntu, siga os passos para instalação de acordo com seu sistema: https://nodejs.org/en/download/package-manager

### Instalando React Native CLI
Com o NodeJS instalado, podemos instalar o CLI (Command Line Interface) do React Native:

**sudo npm install -g react-native-cli**

Ou 

**yarn global add react-native-cli** (Caso prefira usar o yarn, no lugar do npm, mas sua instalaço deve ser feita antes)

### Instalando JDK (Java Development Kit)

Agora precisamos instalar a JDK (Java Development Kit) na versão 8 com o seguinte comando:

**sudo add-apt-repository ppa:openjdk-r/ppa**

**sudo apt-get update**

**sudo apt-get install openjdk-8-jdk**

Obs: A versão 8 do JDK é obrigatória, não utilize versões mais recentes.
Podemos testar a instalação do JDK com o seguinte comando:

_java -version_

### Configurando SDK do Android no Linux

Crie uma pasta em um local desejado para instalação da SDK. Ex: ~/Android/Sdk

Anote esse caminho para ser utilizado posteriormente

Acesse https://developer.android.com/studio/#downloads, na opção "Command line tools only" baixe a SDK referente ao seu sistema operacional.

Após feito o Download, extraia o conteúdo do pacote para a pasta criada no passo anterior.

Com esse endereço precisamos configurar algumas **variáveis ambiente** em nosso sistema, procure pelo primeiro dos seguintes arquivos existentes no seu sistema: ~/.bash_profile , ~/.profile ou ~/.zshrc.

Obs: Para verificar se existe algum desses arquivos, digite **ls -a**, _Ex: User:~$ls -a_ no terminal. Abra com um editor de texto de sua escolha, para facilitar na adição das variáveis de ambiente. No exemplo a seguir, usarei o editor _Gedit_

Ex: gedit .profile

Adicione essas linhas no arquivo (de preferência no início):

export ANDROID_HOME=$HOME/Android/Sdk

export PATH=$PATH:$ANDROID_HOME/emulator

export PATH=$PATH:$ANDROID_HOME/tools

export PATH=$PATH:$ANDROID_HOME/tools/bin

export PATH=$PATH:$ANDROID_HOME/platform-tools

Se nenhum desses arquivos existir, crie o ~/.bash_profile. Caso esteja utilizando uma pasta diferente para a SDK do Android, altere acima.

Agora, abra seu Terminal e execute o seguinte comando:

~/Android/Sdk/tools/bin/sdkmanager  "platform-tools" "platforms;android-27" "build-tools;27.0.3"

**Aceite todas licenças digitando 'y' caso necessário.**
