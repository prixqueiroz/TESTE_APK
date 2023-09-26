## CONFIGURANDO O AMBIENTE - WINDOWS

### 1) VERIFICAR SE O CORDOVA ESTÁ INSTALADO
Para verificar se o Apache Cordova está instalado em seu sistema, você pode usar o terminal/prompt de comando e executar o seguinte comando:

```
cordova -v
```

Se o Cordova não estiver instalado e você quiser instalá-lo globalmente, pode usar o npm para fazer isso. Por exemplo:

```
npm install -g cordova
```

Isso instalará o Cordova globalmente em seu sistema. Certifique-se de ter o Node.js e o npm instalados em seu sistema antes de tentar instalar o Cordova.


### 2) VERIFICAR SE O JAVA JDK 19 ESTÁ INSTALADO
No Prompt de Comando, digite o seguinte comando e pressione Enter:

```
wmic product get description | findstr /i "java"
```

O comando acima listará todos os programas que contêm a palavra "java" em sua descrição. Isso incluirá todas as versões do Java que estão instaladas no sistema.
Verifique se Java(TM) SE Development Kit 19.0.2 (64-bit) está instalado, caso não esteja faça download no link: [https://download.oracle.com/java/19/archive/jdk-19.0.2_windows-x64_bin.exe](https://download.oracle.com/java/19/archive/jdk-19.0.2_windows-x64_bin.exe)

### 3) VERIFICAR SE O GRADLE ESTÁ INSTALADO NO SISTEMA
Para verificar se o Gradle está instalado no sistema, siga estas etapas:
- Abra o terminal ou prompt de comando no seu sistema operacional.
- Execute o seguinte comando para verificar a versão do Gradle instalada:

```
gradle -v
```

Se o Gradle estiver instalado, o comando acima exibirá informações sobre a versão atualmente instalada, como o número da versão, a data de compilação e outras informações relacionadas ao Gradle.

Se o Gradle não estiver instalado e você deseja instalá-lo, você pode fazer isso baixando o Gradle a partir do site oficial [https://gradle.org/next-steps/?version=7.6.1&format=bin](https://gradle.org/next-steps/?version=7.6.1&format=bin) e seguindo as instruções de instalação específicas para o seu sistema operacional.
Descompacta os arquivos e joga no caminho

**C:\Program Files\Gradle**

### 4) VERIFICAR SE O CMDLINE-TOOLS ESTÁ INSTALADO NO SISTEMA
- Abra o Android Studio;
- No menu superior, vá para **"File" > "Settings"**;
- No painel esquerdo,  expanda a seção **"Languages & Frameworks"** e clique em **Android SDK**;
- No painel direito, selecione a guia **"SDK Tools"**;
- Role a lista de ferramentas SDK até encontrar a opção **"Android SDK Command-line Tools"**. Se esta opção estiver marcada (com um check), isso indica que as "cmdline-tools" estão instaladas. Se não estiver marcada, você pode selecioná-la para instalá-las;
- Clique no botão "Apply" ou "OK" para salvar as configurações.

## CONFIGURANDO VARIÁVEIS DE AMBIENTE - WINDOWS

Para todas as várias abaixo o caminho é: Configurações > Sistema > Sobre > Configurações Avançadas do Sistema > Variáveis de Ambiente

### 1) **ANDROID_HOME**
Na seção "Variáveis do sistema", clique em "Novo..." para criar uma nova variável;
No campo "Nome da variável", insira **ANDROID_HOME**;
No campo "Valor da variável", insira o caminho para o diretório onde o Android SDK está instalado **C:\Users\letic\AppData\Local\Android\Sdk**
Clique em "OK" para salvar a variável.

### 2) **ANDROID_SDK_ROO**T
Na seção "Variáveis do sistema", clique em "Novo..." para criar uma nova variável;
No campo "Nome da variável", insira **ANDROID_SDK_ROOT**;
No campo "Valor da variável", insira o caminho para o diretório onde o Android SDK está instalado **C:\Users\letic\AppData\Local\Android\Sdk**
Clique em "OK" para salvar a variável.

### 3) **GRADLE_HOME**
Na seção "Variáveis do sistema", clique em "Novo..." para criar uma nova variável;
No campo "Nome da variável", insira **GRADLE_HOME**;
No campo "Valor da variável", insira o caminho para o diretório onde o Gradle está instalado **C:\Program Files\Gradle**
Clique em "OK" para salvar a variável.


### 4) **JAVA_HOME**
Na seção "Variáveis do sistema", clique em "Novo..." para criar uma nova variável;
No campo "Nome da variável", insira **JAVA_HOME**;
No campo "Valor da variável", insira o caminho para o diretório onde o Java JDK 19 está instalado **C:\Program Files\Java\jdk-19\**
Clique em "OK" para salvar a variável.

### 5) PATH (ou Path)
Na seção **"Variáveis do sistema"**, encontre a variável chamada "Path" e clique em "Editar...".
Na janela "Editar Variável de Sistema", clique em "Novo" e insira o caminho completo para os diretórios (uma entrada para cada linha abaixo):

- **C:\Users\letic\AppData\Roaming\npm\node_modules\cordova\bin\ **
- **C:\Users\letic\AppData\Local\Android\Sdk\platform-tools\ **
- **%**GRADLE_HOME**%\bin**

Na seção **"Variáveis de usuários"**, encontre a variável chamada "Path" e clique em "Editar...".
Na janela "Editar Variável de Sistema", clique em "Novo" e insira o caminho completo para o diretório (uma entrada para cada linha abaixo):
- **C:\Users\letic\AppData\Local\Android\Sdk\cmdline-tools\latest\bin**

## CONVERTER UM SITE HTML PARA UM APLICATIVO APK
Converter um site HTML para um aplicativo APK usando o Cordova envolve vários passos. Certifique-se de seguir cada etapa cuidadosamente. Vou resumir o processo:

**Passo 1: Instale as Pré-Requisitos**

Antes de começar, certifique-se de ter o Cordova instalado (veja as etapas anteriores) e o Android Studio configurado e funcionando. Certifique-se também de ter o Node.js e o npm instalados em seu sistema.

**Passo 2: Crie um Projeto Cordova**

1. Crie um novo projeto Cordova em um diretório de sua escolha:

   ```
   cordova create NomeDoSeuProjeto
   ```

2. Navegue até o diretório do projeto:

   ```
   cd NomeDoSeuProjeto
   ```

**Passo 3: Adicione a Plataforma Android**

Para criar um APK para Android, você precisa adicionar a plataforma Android:

```
cordova platform add android
```

**Passo 4: Adicione seu Conteúdo HTML**

Coloque seu código HTML, CSS, JavaScript e outros recursos na pasta `www` do seu projeto Cordova. Isso é onde você coloca seu site ou aplicativo da web.

**Passo 5: Personalize as Configurações**

Edite o arquivo `config.xml` no diretório do projeto para configurar as propriedades do aplicativo, como nome, versão e descrição.

**Passo 6: Construa o Aplicativo**

Use o seguinte comando para construir o aplicativo:

```
cordova build android
```

Isso irá gerar um arquivo APK não assinado na pasta `platforms/android/app/build/outputs/apk/debug/` (ou uma pasta semelhante, dependendo da versão do Cordova).


**Passo 8: Teste o APK**

Para instalar um arquivo APK (Android Package) em um dispositivo Android, siga os passos abaixo:

1. **Habilitar fontes desconhecidas:** Antes de instalar um APK que não é da Google Play Store, você precisa permitir a instalação de aplicativos de fontes desconhecidas. Para fazer isso:

   - Vá para "Configurações" no seu dispositivo Android.
   - Role para baixo e selecione "Segurança" ou "Privacidade", dependendo da versão do Android.
   - Localize a opção "Fontes desconhecidas" e ative-a. Você será avisado sobre os riscos potenciais ao fazer isso, mas é seguro instalar APKs de fontes confiáveis.

2. **Transferir o APK para o dispositivo:**
   - Você pode baixar o APK diretamente no seu dispositivo ou transferi-lo de um computador usando um cabo USB ou qualquer outra opção de transferência de arquivo (eu envio para mim mesma pelo WhatsApp).

3. **Localizar o APK:** Use um gerenciador de arquivos (por exemplo, o aplicativo "Meus Arquivos" ou "Gerenciador de Arquivos") para navegar até a pasta onde você baixou ou transferiu o APK.

4. **Instalar o APK:** Toque no arquivo APK para iniciar o processo de instalação.

5. **Confirmar a instalação:** Você será solicitado a revisar as permissões que o aplicativo solicita. Leia-as e, se estiver confortável com as permissões, toque em "Instalar" para continuar.

6. **Aguardar a instalação:** O Android instalará o aplicativo e exibirá uma mensagem quando a instalação estiver concluída.

7. **Concluir a instalação:** Depois de instalado, você pode tocar em "Abrir" para iniciar o aplicativo imediatamente ou em "Concluído" para sair da tela de instalação.
